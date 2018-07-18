# Sudoku_solver
Solves all the world's hardest Sudoku puzzles including all from Dr. Arto Inkala, U  of Helsinki (professor of mathematics).
Instructions for using solveit.exe to solve any Sudoku puzzle in the world very quickly. I recompiled it with static linking of run-time libraries so it is not necessary to have Visual Studio installed to run it.

It has two modes of operation:

Mode 1: Manual input mode.

Mode 2: websudoku.com page scrape mode.

In mode 1, a puzzle can be manually typed and saved in a file named i.txt which must reside in the same Windows directory in which the program Sudoku_solver.exe is located. Blanks must be represented with zeroes and each number must be separated by a space.

Mode 1 Example 1:

Suppose you want to see if the program can solve a Sudoku puzzle with the theoretical minimum number of clues, which is 17 clues:

Please note: There are 17 clue puzzles which have no valid solution (invalid puzzle). There are also puzzles with 17 clues which have multiple solutions (invalid puzzle). There are no valid Sudoku puzzles which have less than 17 clues.

Step 1: Download "Sudoku_solver.exe" and "17clues" from this gitHub repository.

Contents of "17 clues":

0 0 0 7 0 0 0 0 0
1 0 0 0 0 0 0 0 0
0 0 0 4 3 0 2 0 0
0 0 0 0 0 0 0 0 6
0 0 0 5 0 9 0 0 0
0 0 0 0 0 0 4 1 8
0 0 0 0 8 1 0 0 0
0 0 2 0 0 0 0 5 0
0 4 0 0 0 0 3 0 0

Step 2: Copy "17clues" to i.txt:

c:\users\youruser\downloads> copy 17clues i.txt

Step 3: Run the program:

c:\users\youruser\downloads> Sudoku_solver.exe


C:\Users\John\Desktop>copy 17clues i.txt
        1 file(s) copied.

C:\Users\John\Desktop>Sudoku_solver.exe

Output:

*****************************************************
checksums
*****************************************************
*****row checksums *****
row[1].checksum=45
row[2].checksum=45
row[3].checksum=45
row[4].checksum=45
row[5].checksum=45
row[6].checksum=45
row[7].checksum=45
row[8].checksum=45
row[9].checksum=45
*****col checksums *****
col[1].checksum=45
col[2].checksum=45
col[3].checksum=45
col[4].checksum=45
col[5].checksum=45
col[6].checksum=45
col[7].checksum=45
col[8].checksum=45
col[9].checksum=45
*****box checksums *****
box[1].checksum=45
box[2].checksum=45
box[3].checksum=45
box[4].checksum=45
box[5].checksum=45
box[6].checksum=45
box[7].checksum=45
box[8].checksum=45
box[9].checksum=45

=====================================================
$$$$$$$$$$$$$    puzzle bl cnt   =0
=====================================================
$$$$$$$$$$$$$    glerr           =0
$$$$$$$$$$$$$    zcnt            =0
$$$$$$$$$$$$$    lzcnt           =4

264 715 839
137 892 645
598 436 271

423 178 596
816 549 723
759 623 418

375 281 964
982 364 157
641 957 382

Elapsed time is: 0 seconds

Congratulations! MANUAL_INPUT  puzzle solved!

Note that puzzle took 0 seconds to solve this puzzle!!!!!






Suppose you want to see if the program can solve the world's hardest Sudoku puzzle, created by Dr. Arto Inkala, Professor of Mathemayics, University of Helsinki. 

Step 1: Download "Sudoku_solver.exe" and "worldshardest" from this gitHub repository.

Contents of "worldshardest:

8 0 0 0 0 0 0 0 0
0 0 3 6 0 0 0 0 0
0 7 0 0 9 0 2 0 0
0 5 0 0 0 7 0 0 0
0 0 0 0 4 5 7 0 0
0 0 0 1 0 0 0 3 0
0 0 1 0 0 0 0 6 8
0 0 8 5 0 0 0 1 0
0 9 0 0 0 0 4 0 0

Step 2: Copy "worldshardest" to i.txt:

c:\users\youruser\downloads> copy worldshardest i.txt

Step 3: Run the program:

c:\users\youruser\downloads> Sudoku_solver.exe

Output:

C:\Users\John\Desktop>copy worldshardest i.txt
        1 file(s) copied.

C:\Users\John\Desktop>Sudoku_solver.exe

*****************************************************
checksums
*****************************************************
*****row checksums *****
row[1].checksum=45
row[2].checksum=45
row[3].checksum=45
row[4].checksum=45
row[5].checksum=45
row[6].checksum=45
row[7].checksum=45
row[8].checksum=45
row[9].checksum=45
*****col checksums *****
col[1].checksum=45
col[2].checksum=45
col[3].checksum=45
col[4].checksum=45
col[5].checksum=45
col[6].checksum=45
col[7].checksum=45
col[8].checksum=45
col[9].checksum=45
*****box checksums *****
box[1].checksum=45
box[2].checksum=45
box[3].checksum=45
box[4].checksum=45
box[5].checksum=45
box[6].checksum=45
box[7].checksum=45
box[8].checksum=45
box[9].checksum=45

=====================================================
$$$$$$$$$$$$$    puzzle bl cnt   =0
=====================================================
$$$$$$$$$$$$$    glerr           =0
$$$$$$$$$$$$$    zcnt            =0
$$$$$$$$$$$$$    lzcnt           =4

812 753 649
943 682 175
675 491 283

154 237 896
369 845 721
287 169 534

521 974 368
438 526 917
796 318 452

Elapsed time is: 137 seconds

Congratulations! MANUAL_INPUT  puzzle solved!



 

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

