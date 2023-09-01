---
layout: project
type: project
image: img/Basic-4-Function-Calculator-Sharp-768x768-371846492.jpg
title: "Java Stack Calculator"
date: 2023
published: true
labels:
  - Java
summary: "A six function calculator with a spanish option"
---

This was for an assignment in the second Java class in the University of Hawaii at Manoa. It's purpose was to improve familiarity of array stacks and linked stacks.

There isn't much to it. The stack is used to buffer number inputs and when an operator is entered, the operation is performed on the numbers stored in the stack.

Here is the code for printing user instructions to the console in English and Spanish.

```cpp
		//instructions for user
		if(spanishMode == true)
		{
			System.out.println("Modo de empleo: escriba un número y pulse Intro,");
			System.out.println("Escriba otro número y presione Entrar,");
			System.out.println("A continuación, escriba el siguiente operador + - * / % ^ y pulse Intro");
			System.out.println("2 + 2 serían:\n");
			System.out.println("2\n2\n+\n\n");
		}
		else
		{
			System.out.println("How to use: type a number and press enter,");
			System.out.println("type another number and press enter,");
			System.out.println("then type in a following operator + - * / % ^ and press enter");
			System.out.println("2 + 2 would be:\n");
			System.out.println("2\n2\n+\n\n");
		}
```
Source Code: https://github.com/JunlangChenGT/javaStackCalculator
