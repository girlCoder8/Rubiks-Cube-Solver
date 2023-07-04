
# Rubiks Cube Solver ![rubik.png](src%2Fres%2Frubik.png)

## Getting Started

### Installation 
1. Clone project using git panel or console. If you not familiar with git, you can simply download ZIP-archive.


1. Setup dependencies (if needed)

Check for jdk setup. It is recommended to use JDK 1.8 or 1.9.
To set up the .jdk go to:
```
File -> Project Structure -> Project -> Project SDK
```

1. Create a folder

Create folder for compiled classed (out by default) and add it to your project structure.
```
File -> Project Structure -> Project -> Project Compiler output
```

### Using .jar file

You can simply run **bin/RubiksCubeSolver.jar** to see how program work. 

## Screenshots

### Solve

To solve just enter your colors to stickers. To do it just click on the color palette and the on sticker. Or just scramble the cube.

![solve.gif](img%2Fsolve.gif)

### Button definition

To solve your cube just enter facelets in the GUI. First click a button on color palette and after a sticker, that you want to pain.
If you want to scramble cube, click that button. To enter rotations, click enter end type your rotation sequins using spaces. 
If you left field empty - cube will be solved.  
 
### Side definition

1. ![#FFFFFF](https://placehold.it/15/FFFFFF/000000?text=+) U - up
1. ![#008000](https://placehold.it/15/008000/000000?text=+) F - face
1. ![#FF0000](https://placehold.it/15/FF0000/000000?text=+) R - right
1. ![#FFFF00](https://placehold.it/15/FFFF00/000000?text=+) D - down
1. ![#FFA500](https://placehold.it/15/FFA500/000000?text=+) L - left
1. ![#0000FF](https://placehold.it/15/0000FF/000000?text=+) B - back

## How algorithm works?

All cube solving process split into two subgroups. In each phase only special moves allowed.
*Simply program just move cube from start to middle state, and after to solve state, using allowed below moves.*

```
    G0 = <U, D, L, R, F, B>
    G1 = <U, D, L2, R2, F2, B2>
```

In phase 1, the algorithm looks for maneuvers which will transform a scrambled cube to G1.
That is, the orientations of corners and edges have to be constrained and the edges of the UD-slice have to be transferred into that slice.

In phase 2 the algorithm restores the cube in the subgroup G1, using only moves of this subgroup. 
It restores the permutation of the 8 corners, the permutation of the 8 edges of the U-face and D-face and the permutation of the 4 UD-slice edges. 
 
The algorithm does not stop when a first solution is found but continues to search for shorter solutions by carrying out phase2 from suboptimal solutions of phase1. 






