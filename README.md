
# **Project: Star Trek Warp Wars**

**Aim of the Project:** The aim of this project is to develop a robot "space maze" game where players navigate a maze, collect treasures, and compete for the highest end-game score.

**General Information:**

-   The game is played on a 23x55 grid with walls.
-   Two competitors: Player ( P ) and Computer ( C ).
-   Treasures/numbers are collected to increase scores.
-   The objective is to achieve the highest end-game score.

**Game Elements:**

-   P: Player
    
    -   Controls P using cursor keys.
    -   Has a backpack (size of 8 elements).
    -   Uses WASD keys to remove an element from the backpack.
    -   Has energy for quick movement (2 times faster).
-   C: Computer robots
    
    -   Controls all C robots.
    -   Treasures are 2 times valuable for the computer.
    -   C robot selects a target and tries to move directly to it.
-   Numbers (1-5): Treasure elements
    
    -   1-3: Static numbers.
    -   4-5: Moving numbers.
-   Other treasures:
    
    -   =: Trap device.
    -   *: Warp device.

**Input Queue:**

-   Elements are inserted into the maze from an input queue.
-   The queue is always full (size of 15 elements).
-   Shows the next element to be inserted into the maze.
-   Elements are inserted at random places every 3 seconds.

**Treasure Points, Probabilities, and Generation:**

| Treasure | Score (Player) | Score (Computer) | Generation Probability |
|----------|-----------------|------------------|-------------------------|
| 1        | 1               | 2                | 12/40                   |
| 2        | 5               | 10               | 8/40                    |
| 3        | 15              | 30               | 6/40                    |
| 4        | 50              | 100              | 5/40                    |
| 5        | 150             | 300              | 4/40                    |
| =        | -               | 300              | 2/40                    |
| *        | -               | 300              | 1/40                    |
| C        | 300             | -                | 2/40                    |


**Game Initialization:**

-   Load the game area from the "maze.txt" file.
-   Place P and one C robot randomly in the maze.
-   P starts with 5 lives and energy for 50 seconds.
-   Place the first 20 elements of the input queue into the maze.

**Game Playing Information:**

-   Players collect numbers by reaching their squares.
-   Movements are in 4 directions (no diagonal).
-   Normal speed: 2 frames per second.
-   P's quick movement is 2 times faster.
-   P loses quick movement without energy.
-   P loses a life when a C robot reaches its square.
-   End game when P loses all 5 lives.

**Backpack and Elements:**

-   P collects score points and places numbers in the backpack.
-   Two identical numbers in the backpack turn into a power or device.
-   Remove elements from the backpack using WASD keys.

**End-Game Score Calculation:**

-   End-Game Score of the Human Player = P.Score - C.Score
