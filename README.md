# Sudoku_solver
Solves all the world's hardest Sudoku puzzles including all from Dr. Arto Inkala, U  of Helsinki (professor of mathematics).
Instructions for using solveit.exe to solve any Sudoku puzzle in the world very quickly. I recompiled it with static linking of run-time so it is not necessary to have Visual Studio installed to run it.

It has two modes of operation. A puzzle can be manually created by saving or typing a puzzle as I.txt filename. A bit tedious, unless one wants to test the program against the hardest in the world.

5 0 3 2 0 0 0 0 0  line 1
…

2 0 0 5 0 0 0 0 3   line 9

save as I.txt  and then type solveit from the same directory.

A much cooler, easier to test the program is to click on puzzles in the websudoku site (must use Chrome). 

Type sudoku. It will be the first website. Pick an EASY puzzle.

The program will scrape the selected puzzle off the website if you right click  “view frame source” and then right click and save frame source as whatever file Chrome picks. 

When the frame source is saved, it must be saved as “HTML only” instead of “complete web page”.

Once that file is saved to your download directory, close the frame html tab and open a dos command prompt window (I know. The heuristic “human approach” algorithms used up all the juice on “back end”). Path needs to be your download path like C:\users\me\Desktop.Wherever you put solveit.

Type solveit and it will be solved in 0 seconds, most likely. You can type the puzzle into to the web page to check it if you like to see if the answer is right, but it is a waste of time. The program will never display an incorrect answer. It is not possible. A valid Sudoku puzzle has only one correct solution and my program does a check of rows, columns and boxes and they must all add up to 45. Scroll back and you can see the verification checksum.

Pick a medium puzzle.

Right click “view frame source”.  

Right click “save as”  chrome default filename and “HTML only” file type (should already be filled in).

Close the HTML tab. Resize the puzzle on the left and the dos window on the right.

Up arrow and enter (solveit)

Probably zero seconds.

Pick a hard puzzle.

Repeat medium steps as above.

Probably 0 or maybe 1 second depending on how slow you computer is.

Pick an EVIL puzzle same thing.

You could do this a million times and this program will never fail or give a wrong answer.

See image files for Chrome websudoku.com puzzle page scrape instructions and manual puzzle input instructions.

It is written in C++ (C++11 library for Marsenne Twister random number generator) and compiles with no warnings in Visual Studio. Since I recompiled it with static linking of needed runtime DLLs, it is a stand-alone exe. 

It can solve the hardest Sudoku puzzles in the world.

A lot of email providers don’t like or allow .EXE files to be sent as mail attachments, so copying it from my  Github is the easiest:

