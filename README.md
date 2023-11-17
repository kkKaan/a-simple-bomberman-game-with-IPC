# Bomberman Game with IPC

## Overview
This project presents a C-based text Bomberman game leveraging inter-process communication (IPC). Players navigate a maze, plant bombs, and aim to be the last one standing. The game employs bidirectional pipes for communication and involves complex game logic for bomber and bomb behaviors.

## Features
- Text-based maze environment.
- Multiple players with unique initiatives.
- Bomb planting with explosion mechanics affecting bombers and obstacles.
- Bidirectional pipe communication using `socketpair()`.
- Select/Poll system calls for non-blocking I/O.

## Prerequisites
- C compiler (e.g., GCC)
- Linux-based OS for system calls compatibility

## Compilation and Execution
1. Clone the repository.
2. Navigate to the project directory.
3. Compile the game using the provided Makefile.
4. Run the game with `./bgame`.

## Game Mechanics

### Bombers
- **Initiative**: Order of message sending.
- **Movement**: One step at a time in the maze.
- **Obstacle Vision**: Limited visibility with obstacle considerations.
- **Bomb Planting**: At current location, fails if a bomb is already present.
- **Death**: Occurs on explosion impact.

### Bombs
- **Explosion Mechanics**: Timed explosions with a cross pattern.
- **Obstacle Interaction**: Obstacles block and can be destroyed by explosions.
- **Player Elimination**: Bombs can eliminate bombers, including self-elimination.

### Controller Logic
- **Socket Monitoring**: Using `select()` or `poll()` for bomb and bomber sockets.
- **Game Progression**: Manages game state, including ending conditions.

## Code Structure

- `bgame.c`: Main game file containing logic, bomber and bomb management, and IPC mechanisms.
- `bomb`: Executable for managing bomb explosions.
- Additional utility and header files for supporting functionalities.

## Additional Information
For a detailed game description, refer to the included PDF documentation.
