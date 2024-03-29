# Team Implementation Report

## Technical Diagrams

![image](https://user-images.githubusercontent.com/56427412/183280065-c3e083e0-a3c4-4a2d-ac9f-163271ed764d.png)

## Technical Description

* There are two main python files that are required for the program to be executed properly. This first python file is the Sudoku-Solver program and the second file contains a list of Sudoku grids. 

* The Sudoku-Solver program is organized in a functional programming structure. It is mainly organized into seven sections: 
1.	Grid generation – This section contains only one function. This function will print a screen display of the grid, the given numbers and the button to proceed to solve the grid. 
2.	Execution of first algorithm and analysis – This section contains three functions. The first function tests the validity of the number in the cell. The second function allows the algorithm to traverse through the grid. The third function prints the solving process onto the screen, along with the indicators for algorithm analysis. 
3.	Execution of second algorithm and analysis – This section contains seven functions. The first function finds an empty cell in the grid. The next four functions test the validity of the number in the cell. The sixth function allows the algorithm to traverse through the grid. The final function prints the process onto the screen, along with the indicators for algorithm analysis.
4.	Display of analytics report of both algorithms – This section contains one function. This function will gather the data from both algorithms and display it on the screen.
5.	Selection of next difficulty level– This section contains one function. This functions will allow the user to choose “easier” or “difficult” for the generation of the new grid. 
6.	Generation of new grid based on difficulty selection – This section contains two functions. The first function will process the indicators by selecting the faster algorithm (depending on the indicators) and produce certain values that will ensure that the next grid is easier or harder, depending on what the user chooses. The second function will accept these values, and choose a grid from the list of grids given.  
7.	Main function –This main function will loop through the above six sections repeatedly.  

* The second python file contains a list Sudoku grids that are stored in a nested list format. The Sudoku grids have been arranged based on their levels of difficulty. Each Sudoku grid has a specific index, which can be called in the main function. 

## Algorithms and Data Structures

* The data structure for the Sudoku grid is a nested list. There are nine lists (of nine numbers) nested within a single list. The single list will serve as the Sudoku grid, which will be called by the Sudoku solver. 

* The algorithms used to solve the Sudoku puzzles are backtracking algorithms. The second algorithm (used by the Smart Game Solver) is a more optimized version than the first. The backtracking algorithm traverses across the Sudoku grid, from left to right, and from up to down. The algorithm will visit every empty cell sequentially, starting from the cell in the first row and first column. At every empty cell, the numbers 1 to 9 will be incrementally placed into the cell, and the number will be tested for validity. If the number is valid, the number is fixed into the cell, and thee algorithm will move to the next cell. If the numbers 1 to 9 all fail to be valid, a number 0 is placed into the cell, and the algorithm will return to the previous cell and the number is increased by 1. This process will carry on until all the cells are filled. 

## Imported Libraries 

* The libraries that were imported were pygame, time, json and random. Pygame is the main library used to construct the Sudoku game. The time library is used to calculated the time taken for the algorithm to solve the grid. The json library was used to create a copy of the grid. The random library is used to generate a random number. 

## Known Issues

* There was an issue with removing the “answers” from the grid when program moved the second algorithm. As a result, the second algorithm always received an already solved grid, and it took 0 seconds to solve the Sudoku grid. This was due to an issue with the memory address of the Sudoku grid. It was corrected by creating a copy of a grid in the computer’s memory address. 

* When the backtracking algorithm was being executed to solve the puzzle, sometimes the numbers were not printed out properly to the screen. This resulted in the Sudoku puzzle looking incomplete, though the puzzle had been solved in the computer memory. This was due to the speed at which the numbers were printed. It was corrected by inserting a 2.5ms delay between each number print.

* For both the algorithms, the calculated “errors” were always higher than the “tries”. However, logically the “tries” ought to be more than the “errors”. This bug has not been rectified.  
