## Gomoku with Forbidden Move Support
> C language major project, the version that fixed the bug in the hash table (by removing the hash table altogether)

## Compile
### Visual Studio 2015
Please compile using the release configuration, and ensure that the (default) `/O2` optimization is turned on.

### CMake
It is recommended to compile using `CMake`, which generates the executable file `five`(Linux)/`five.exe`(Windows)
```bash
cmake .
make
```

### gcc
```bash
gcc --std=c99 -O3 *.c -o five
```

### Possible Compilation Errors and Solutions
1. game.c includes characters for drawing the chess board, which are in GB2132 encoding. If a compilation error occurs, change the encoding of that file to GB2132. (Windows only)
2. Please use the c99 standard or above.

## Notes
- The AI's level corresponds to the search depth +1 (this version can search 6 levels), level 6 is too slow and ineffective.
- Unable to judge complex forbidden moves.

## Algorithms
1. `acm.c`: Aho-Corasick automaton (used for pattern matching), used for scoring functions and forbidden move judgment.
2. `bot.c`: AI implementation (game search + AlphaBeta pruning).
3. `five.c`: Program entry point.
4. `game.c`: Game logic (mode logic, interaction, win/loss judgment).
5. `scores.h`: Scoring/forbidden move judgment table.
6. `utilities.h`: Contains implementations of queues and doubly-linked lists for heuristic optimizations.
