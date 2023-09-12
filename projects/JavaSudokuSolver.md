---
layout: project
type: project
image: img/easy+sudoku+to+print-1937610920.jpg
title: "Java Sudoku Solver"
date: 2023
published: true
labels:
  - Java
  - Recusion
summary: "Recursive brute force method for solving sudoku"
---

This was for an assignment in the second Java class in the University of Hawaii at Manoa. It was the second assignment concerning recursive methods.

My professor, Edoardo Biagioni, wrote the SudokuTest class and placed incomplete sudoku squares for our methods to complete. I (with much help of my teaching assistants), wrote the fillSudoku and getValues methods to solve the sudoku.

Here is the helper method used to guess the value of a cell.

```cpp
	public static java.util.ArrayList<Integer> getValues(int[][] sudoku, int row, int col)
	{
		boolean[] values = new boolean[10];

		//check for invalid values in the row
		for(int i = 0; i < sudoku.length; i++)
		{
			int cell = sudoku[row][i];
			if(cell != 0) values[cell] = true;
		}

		//check for invalid values in the column
		for(int i = 0; i < sudoku.length; i++)
		{
			int cell = sudoku[i][col];
			if(cell != 0) values[cell] = true;
		}

		//check for invalid values in the 3x3 square
		int startRow = row - (row % 3);
		int startCol = col - (col % 3);
		for(int i = 0; i < 3; i++)
		{
			for(int j = 0; j < 3; j++)
			{
				int cell = sudoku[startRow + i][startCol + j];
				if(cell != 0) values[cell] = true;
			}
		}

		java.util.ArrayList<Integer> list = new java.util.ArrayList<>();
		for(int i = 1; i < values.length; i++)
		{
			if(!values[i]) list.add(i);
		}
		return list;
	}
```
[Source Code](https://github.com/JunlangChenGT/JavaSudokuSolver)
