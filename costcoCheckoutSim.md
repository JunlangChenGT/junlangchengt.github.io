---
layout: project
type: project
image: img/micromouse/micromouse-square.jpg
title: "Retail Checkout Simulation"
date: 2023
published: false
labels:
  - Simulation
  - Java
summary: "A simulation concerning customer wait times during checkout comparing Costco-esque and Ross-esque customer queues."
---

<div class="text-center p-4">
  <img width="200px" src="../img/micromouse/micromouse-robot.png" class="img-thumbnail" >
  <img width="200px" src="../img/micromouse/micromouse-robot-2.jpg" class="img-thumbnail" >
  <img width="200px" src="../img/micromouse/micromouse-circuit.png" class="img-thumbnail" >
</div>

This was an assignment in the second Java class in the University of Hawaii at Manoa. It was supposed to increase proficiency in implementing queue structures.

The simulation simulates every second in a 24 hour span. There are a total of 5000 customers with randomized arrival and service times to simulate the checkout process at the cashier. A linked list of customer objects represent the checkout line in the Ross case, and 10 queues in the Costco case. Both types have 10 cashiers at the end of the line. For the multi-queue, customers enter the shortest available line but do not move to shorter lines if another line gets shorter. The wait time in line before reaching the cashier is logged and averaged over every customer served.  Over multiple runs of the simulation, the average wait time of the Costo-esque multi line was around 270 seconds while the Ross-esque single line averaged around 170 seconds. This is thought to be the result of the single queue not having cashier downtime.

Here is some code for polling customers from the end of the line:

```cpp
//pull the customer from the line
				for(int i = 0; i < cashiers.length; i++)
				{
					if( (cashiers[i] == -7) && (customersBeingServed[i] == null) && !queues[i].isEmpty() )
					{
						//System.out.println("b" + i);
						customersBeingServed[i] = queues[i].poll();
						cashiers[i] = currentTime + customersBeingServed[i].serviceTime;
						customersBeingServed[i].waitTime = currentTime - customersBeingServed[i].waitTime;
						//get wait time by subtracting previous time by current time
						waitTimeArray[customersBeingServed[i].indexInCustomersArray] = customersBeingServed[i].waitTime;
						//add the time to the array
					}
					
					if( (customersBeingServed[i] != null) && (currentTime == cashiers[i])) 
					{
							
							cashiers[i] = -7;
							totalCustomersServed++;
							customersBeingServed[i] = null;
					}
					
				}
```

