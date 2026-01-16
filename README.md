# Minesweeper Game - C++ Edition

A classic Minesweeper game built with C++ and SFML (Simple and Fast Multimedia Library), featuring clean graphics and smooth gameplay.

![C++](https://img.shields.io/badge/C++-11+-blue.svg)
![SFML](https://img.shields.io/badge/SFML-2.5+-green.svg)

## Features

- **Classic Minesweeper Gameplay**: Authentic recreation of the classic puzzle game
- **Interactive GUI**: Built with SFML for smooth graphics and responsive controls
- **Mine Detection**: Left-click to reveal cells, right-click to place flags
- **Win/Loss Detection**: Automatic game state detection
- **Clean Graphics**: Professional-looking interface with clear visual feedback
- **Recursive Reveal**: Automatically reveals adjacent safe cells

## Screenshots

*Game interface showing the Minesweeper grid and controls*

## Installation

### Prerequisites

- **C++ Compiler**: Visual Studio 2019+ (or any C++11 compatible compiler)
- **SFML Library**: Version 2.5 or higher
- **Windows OS**: (Primary development platform)

### Setup Instructions

#### 1. Clone the Repository
```bash
git clone https://github.com/Luis-B97/Minesweeper-CPP.git
cd Minesweeper-CPP
```

#### 2. Install SFML

**Option A: Download Pre-built SFML**
- Download SFML from: https://www.sfml-dev.org/download.php
- Choose the version matching your Visual Studio compiler
- Extract to a known location (e.g., `C:\SFML`)

**Option B: Use vcpkg (Recommended)**
```bash
vcpkg install sfml
```

#### 3. Configure Visual Studio Project

1. Open the `.sln` file in Visual Studio
2. Right-click project → Properties
3. **C/C++ → General → Additional Include Directories**: Add SFML include path
   - Example: `C:\SFML\include`
4. **Linker → General → Additional Library Directories**: Add SFML lib path
   - Example: `C:\SFML\lib`
5. **Linker → Input → Additional Dependencies**: Add SFML libraries
   - Debug: `sfml-graphics-d.lib;sfml-window-d.lib;sfml-system-d.lib;`
   - Release: `sfml-graphics.lib;sfml-window.lib;sfml-system.lib;`

#### 4. Copy SFML DLLs

Copy SFML DLLs from `SFML\bin` to your project's output directory:
- `sfml-graphics-2.dll`
- `sfml-window-2.dll`
- `sfml-system-2.dll`

#### 5. Build and Run

- Build the project (F7)
- Run the game (F5)

## How to Play

### Game Rules

1. **Goal**: Reveal all cells that don't contain mines
2. **Numbers**: Show how many mines are adjacent to that cell
3. **Flags**: Mark cells you believe contain mines
4. **Win**: Reveal all safe cells without hitting a mine
5. **Loss**: Click on a cell containing a mine

### Controls

| Input | Action |
|-------|--------|
| **Left Click** | Reveal cell |
| **Right Click** | Place/remove flag |
| **Debug Mode** | Show all mine locations |

### Game Tips

- Start with corners and edges
- Use numbers to deduce mine locations
- Flag suspected mines to avoid accidental clicks
- Look for patterns (1-2-1, 1-2-2-1, etc.)

## Project Structure

```
Minesweeper-CPP/
├── Source Files/
│   ├── main.cpp              # Entry point and game loop
│   ├── Board.cpp             # Game board logic
│   ├── Cell.cpp              # Individual cell behavior
│   └── Game.cpp              # Game state management
├── Header Files/
│   ├── Board.h               # Board class definition
│   ├── Cell.h                # Cell class definition
│   └── Game.h                # Game class definition
├── Assets/
│   ├── textures/             # Sprite images
│   └── fonts/                # Text fonts
└── README.md                 # This file
```

## Technical Details

### Architecture

- **Object-Oriented Design**: Utilizes classes for Board, Cell, and Game management
- **Event-Driven**: SFML event handling for user interactions
- **Recursive Algorithm**: For revealing adjacent safe cells
- **Grid System**: 2D array-based board representation

### Key Algorithms

**Mine Generation**
- Random placement with configurable mine count
- Ensures valid board states

**Recursive Reveal**
- Flood-fill algorithm for revealing connected safe cells
- Stops at numbered cells

**Win Detection**
- Tracks revealed cells vs. total safe cells
- Updates game state accordingly

### SFML Components Used

- **Graphics Module**: Rendering sprites and text
- **Window Module**: Creating and managing the game window
- **System Module**: Timing and vector utilities

## Configuration

You can modify game settings in the source code:

```cpp
// Example configuration options
const int BOARD_WIDTH = 10;   // Number of columns
const int BOARD_HEIGHT = 10;  // Number of rows
const int MINE_COUNT = 15;    // Number of mines
const int CELL_SIZE = 32;     // Pixel size of each cell
```

## Development

### Built With

- **Language**: C++11
- **Graphics Library**: SFML 2.5+
- **IDE**: Visual Studio 2022
- **Compiler**: MSVC (Microsoft Visual C++)

### What I Learned

- Game development with SFML
- Event-driven programming
- Recursive algorithms (flood-fill)
- Object-oriented design patterns
- Working with 2D arrays and grid systems
- Graphics rendering and sprite management
- Resource management in C++

## Future Enhancements

- [ ] Multiple difficulty levels (Easy, Medium, Hard)
- [ ] Custom board sizes
- [ ] Timer and scoring system
- [ ] Leaderboard/high scores
- [ ] Sound effects and music
- [ ] First-click safety (never hit mine on first click)
- [ ] Hint system
- [ ] Save/load game state

## Troubleshooting

### Common Issues

**SFML DLLs Not Found**
- Ensure SFML DLLs are in the same directory as the executable
- Or add SFML\bin to your system PATH

**Linker Errors**
- Verify SFML library paths in project properties
- Check that you're using the correct SFML version for your compiler
- Ensure Debug/Release configurations match SFML library types

**Graphics Not Displaying**
- Check that texture/image files are in the correct path
- Verify working directory is set to project directory

## Contributing

This is a personal educational project, but suggestions and feedback are welcome!

## License

This project was created for educational purposes.

## Acknowledgments

- SFML Documentation and Community
- Classic Minesweeper by Microsoft
- University coursework inspiration

## Contact

Luis B - [GitHub](https://github.com/Luis-B97)

---

**Note**: This project demonstrates C++ programming skills, game development concepts, and working with external libraries like SFML.
