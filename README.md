# PCA_Project
Solving the Numberlink Problem
/*All Links are from external sources and contains credits to original authors.*/

I am trying to solve NumberLink puzzle using Logic programming for the project.
The puzzle is available as android App called "Flow".

It is an NP Complete Logic problem .
As wikipedia says: "As a computational problem, finding a solution to a given Numberlink puzzle is NP-complete"
https://en.wikipedia.org/wiki/Numberlink


#Problem Description:
Number Link is a Japanese pencil puzzle game published by Niko

Rules for the game can be given as below:

1).Connect pairs of the same numbers with a continuous line.
2. Lines go through the centre of the cells, horizontally, vertically, or changing direction, and never twice through the same cell.
3. Lines pass through all unnumbered cells, and cannot cross, branch o , or go through the cells with numbers


An example pseudocode  for the approach is given as :

1)Locate squares (i, j) and (k, l) randomly on the board such that:
    (a) (i, j) and (k, l) are neighbors of one another, and
    (b) neither (i, j) nor (k, l) belongs to any path generated so far.
    If no such pair of squares is found on the entire board, return FAILURE    
    /* Here, (i, j) and (k, l) are the first two squares on the new path to be constructed. */

2)  Make a union of the two union-find trees containing (i, j) and (k, l).
   
3)  Repeat so long as the current path can be extended:
    Rename (i, j) = (k, l).
    Locate a random neighboring square (k, l) of (i, j) such that:
    (a) (k, l) does not belong to any path generated so far (including the current one)
    (b) the only neighbor (k, l) has on the partially constructed current path is (i, j).
 
4)    If no such neighbor (k, l) can be found, the path cannot be extended further, so break the loop
   
5)  Otherwise, make the union of the two union-find trees to which (i, j) and (k, l) belong.

6)  Set the endpoint flags of the two squares that are at the beginning and at the end of the new path.

7)  Return SUCCESS

http://www.geeksforgeeks.org/a-number-link-game/

More optimized and sophisticated methods were produced in this study : 
www.mdpi.com/1999-4893/5/2/176/pdf
www.informatik.uibk.ac.at/en/teaching/smb/theses/64.pdf

I am planning to make a logic rules driven solution for the same in IDP, as to the best of my knowledge no IDP Program has been published for the same.

A Picat Program for is given at : https://github.com/hakank/hakank/blob/master/picat/numberlink.pi

A Comparison of the two approaches will be made to understand both the solutions better.

