# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver
# Question 1(Naked Twins)

Q: How do we use constraint propagation to solve the naked twins problem?

A: Constraint propagation is a method of inference that assigns values to variables characterizing a problem in such a way that some conditions (called constraints) are satisfied. (Winston, P. (1993). Artificial Intelligence (3rd ed.). Addision-Wesley)
Naked Twins mean that there are only two options. They are simply two squares within the same unit which have only two possible yet identical values.
The strategy to solve sudoku using naked twins is as follows: First we find naked twins, pairs of identical values within each unit. Then we eleminate the digits of the naked twins from the other boxes in the unit. And we apply this constraint repeatedly until the Sudoku puzzle stops changing.

The code snippet below presents the method of implementing constraint  using naked twins. There are two situations we deal with.
First, naked twins function should take a puzzle and check the current state for naked twins. If there are none, then there is nothing to do.
![Sudoku|naked_twins](https://cldup.com/kabesP69uK.png)

Search helper function is calling reduce_puzzle properly. We use naked twins as part of the strategy to solve sudoku. In this case, we add a call to naked twins in the same place we call eliminate and only_choice.
![Sudoku|reduse_puzzle](https://cldup.com/iSW0QZArzV.png)

# Question 2(Diagonal Sudoku)

Q: How do we use constraint propagation to solve the diagonal sudoku problem?

A: Diagonal sudoku is a special type of sudoku with diagonal constraint. We use the same constraint propagation method as for regular sudokus.
To solve the diagonal sudoku problem, we don't need to modify the constraint propagation code itself. 
We only create two additional units that represent the diagonals of the grid. Once this is done, all the diagonal entries will have the corresponding diagonal entries as their peers. 
The code snippet below presents the method of implementing diagonal constraint.
![Sudoku|cross](https://cldup.com/LnAGvyRgxc.png)
