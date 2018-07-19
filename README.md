Sudoku_solver
Solves all the world's hardest Sudoku puzzles including all from Dr. Arto Inkala, U  of Helsinki (professor of mathematics).
I recompiled the C++ source code Sudoku_solver.cpp with static linking of run-time libraries in Visual Studio so it is not necessary to have Visual Studio installed to run it.

Note: This proram makes use of two c++11 libraries, chrono and random:

This is done so that the wonderful 64-bit Mersenne twister random number generator mt19937_64 generator(gseed) can be used. The standard C++ rand(seed) is uselessly unrandom.  This is  transparent though since those two libraries are statically linked. Initial seed is derived from the system clock.

To change it to run in a Linux environment requires editing the Sudoku_solver.cpp file and editing 2 lines to change _tmain to main and then recompiling with gcc.
========================================
It has two modes of operation:

Mode 1: Manual input mode.

Mode 2: websudoku.com page scrape mode.
=========================================

In mode 1, a puzzle can be manually typed and saved in a file named i.txt which must reside in the same Windows directory in which the program Sudoku_solver.exe is located. Blanks must be represented with zeroes and each number must be separated by a space.
==========================================
Mode 1 Example 1:

Suppose you want to see if the program can solve a Sudoku puzzle with the theoretical minimum number of clues, which is 17 clues:

Please note: 
There are 17 clue puzzles which have no valid solution (invalid puzzle). 
There are 17 clue puzzles which have multiple solutions (invalid puzzle). 
There are no Sudoku puzzles which have less than 17 clues which only have one unique solution (valid puzzle).
===============================================================================
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

================================
Step 2: Copy "17clues" to i.txt:

C:\Users\John\Desktop>copy 17clues i.txt
        1 file(s) copied.
================================ 
Step 3: Run the program:

C:\Users\John\Desktop>Sudoku_solver.exe
=======================================
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

======================================================================================================================================
It is impossible for this program to output a wrong answer for any puzzle with only one solution. This is accomplished by checksumming each row, column and box in the answer output. See above. All values will add up to 45: 1+2+3+4+5+6+7+8+9 = 45.
======================================================================================================================================
If a wrong answer had been calculated, several rows, columns and boxes would would have oddball summations like 43, 41, 46 etc.

Since only results summing up to 45 are allowed, wrong answers are thusly prohibited.

A Sudoku puzzle contains 9 rows of 9 numbers. 81 numbers total. The puzzle can be viewed in different ways:

9 rows of 9:

row_type row[rmax];

Example from 17clues input puzzle):

row[1] = 0 0 0 7 0 0 0 0 0

9 columns of 9:

col_type col[cmax];

Example (from 17clues input puzzle):

col[1] =
0
1 
0
0
0
0
0
0
0
 
9 3 x 3 boxes of 9:

box_type box[bmax];

Example (from 17clues input puzzle):
box[1] = 

0 0 0      
1 0 0        
0 0 0       
 
3 "row units" of 3 horizontal 3 x 3 boxes:

row_unit rowunit[rumax];

Example (from 17clues answer output):

row_unit[1] = 

264 715 839
137 892 645
598 436 271

3 "column units" of 3 vertical 3 x 3 boxes:

col_unit colunit[cumax];

Example (from 17clues answer output):

col_unit[1] = 

264            
137           
598    

423   
816          
759         

375            
982         

Ora single 2-dimensional 9 x 9 array of digits 1 through 9:

int puzzle[rmax][cmax];

Example (from 17clues answer output):

puzzle[1..9][1..9] = 

264 715 839
137 892 645
598 436 271

423 178 596
816 549 723
759 623 418

375 281 964
982 364 157
641 957 382

++++++++++++++++++++++++++++++++++++++++++++++++++

Mode 1 Example 2:
=================
Suppose you want to see if the program can solve the world's hardest Sudoku puzzle, created by Dr. Arto Inkala, Professor of Mathematcs, University of Helsinki.

Dr. Inkala told me about this puzzle:  "I ran chi-square regressions non-stop for a month on a supercomputer to create the world's hardest puzzle".

 It does indeed live up to it's name!
====================================================================================
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

======================================
Step 2: Copy "worldshardest" to i.txt:

C:\Users\John\Desktop>copy worldshardest i.txt
 1 file(s) copied.
=======================================
Step 3: Run the program:

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
=============================================================
Note that this puzzle took an incredible 137 seconds to solve!

That is the longest run time of any of Arto's "Top 10 hardest" or any other puzzle, proving that Dr. Inkala was right!

The average EVIL level puzzle on websudoku.com takes 0-1 seconds.

======================
Mode 2 (Chrome only!):
======================

Mode 2 is a handy way to test many, many puzzles. I created this mode to prove that Sudoku_solver will solve every single one of the 

3,524,523,076 "Easy"-level puzzles on the site.

Every single one of the 4,193,045,015 "Medium"-level puzzles on the site.

Every single one of the 6,024,188,247  "Hard"-level puzzles on the site.

Every single one of the 10,370,837,067  "EVIL"-level puzzles on the site.

By automating the puzzle extraction process down to a few mouse clicks and then hitting <up arrow><enter> to solve the current puzzle displayed on the web page, the doubter of the infallibility of my program can test all 24112593405 puzzles, if so desired.

Type sudoku. It will be the first website. Pick an EASY puzzle.

Select an "Easy" puzzle.

The program will scrape the selected puzzle off the website if you right click  “view frame source” and then right click and save frame source as whatever file Chrome picks. 

When the frame source is saved, it must be saved as “HTML only” instead of “complete web page”.

Once that file is saved to your download directory, close the frame html tab and open a dos command prompt window (I know. The heuristic “human approach” algorithms used up all the juice on “back end”). Path needs to be your download path.

Type Sudoku_solver.exe and it will be solved in 0 seconds, most likely. You can type the puzzle into to the web page to check it if you like to see if the answer is right, but it is a waste of time. The program will never display an incorrect answer.  

Pick a medium puzzle.

Right click “view frame source”.  

Right click “save as”  chrome default filename and “HTML only” file type (should already be filled in).

Close the HTML tab. Resize the puzzle on the left and the dos window on the right.

Up arrow and enter (solveit)

Probably zero seconds.

Pick a hard puzzle.

(Repeat medium steps as above).

Probably 0 or maybe 1 second depending on how slow you computer is.

Pick an "EVIL" puzzle and do same steps as above.

You could do this a million times and this program will never fail or give a wrong answer.

Thank you!

Marion Barbee Jr.

Highland Village, Texas 75077

July 18. 2018

Contact: buddybarbee@yahoo.com



 
