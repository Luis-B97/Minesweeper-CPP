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
- **Configurable Settings**: Game settings loaded from `config.cfg`

## Screenshots

*Classic Minesweeper gameplay with SFML graphics*

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

#### 3. Open in Visual Studio

1. Open `Project3_Minesweeper.sln` in Visual Studio
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

### Game Tips

- Start with corners and edges
- Use numbers to deduce mine locations
- Flag suspected mines to avoid accidental clicks
- Look for patterns (1-2-1, 1-2-2-1, etc.)

## Project Structure

```
Minesweeper-CPP/
├── SFML_Demo/                    # Main project folder
│   ├── Project3_Minesweeper.cpp  # Main game logic and entry point
│   ├── Controller.h              # Game controller class
│   └── Tile.h                    # Tile/Cell class definition
├── images/                       # Game sprite assets
│   ├── debug.png
│   ├── digits.png
│   ├── face_happy.png
│   ├── face_lose.png
│   ├── face_win.png
│   ├── flag.png
│   ├── mine.png
│   ├── number_*.png             # Number sprites (1-8)
│   ├── tile_hidden.png
│   └── tile_revealed.png
├── config.cfg                    # Game configuration file
├── Project3_Minesweeper.sln     # Visual Studio solution file
├── .gitignore                   # Git ignore file
└── README.md                    # This file
```

## Configuration

Game settings are loaded from `config.cfg`:

```
# Example config.cfg format
width=25        # Board width (columns)
height=16       # Board height (rows)
mines=50        # Number of mines
```

Modify these values to adjust game difficulty.

## Technical Details

### Architecture

- **Object-Oriented Design**: 
  - **Controller Class**: Manages game state, board generation, and game logic
  - **Tile Class**: Represents individual cells with state (revealed, flagged, mine)
- **Event-Driven**: SFML event handling for mouse clicks
- **Recursive Algorithm**: For revealing adjacent safe cells
- **Grid System**: 2D array-based board representation

### Key Components

**Controller (`Controller.h`)**
- Game initialization and board setup
- Mine placement algorithm
- Win/loss detection
- User input handling
- Rendering game state

**Tile (`Tile.h`)**
- Individual cell properties
- State management (hidden, revealed, flagged)
- Mine status
- Adjacent mine count

**Main Game Loop (`Project3_Minesweeper.cpp`)**
- SFML window creation
- Event polling
- Game state updates
- Rendering sprites

### SFML Components Used

- **Graphics Module**: Rendering sprites, textures, and text
- **Window Module**: Creating and managing the 800x576 game window
- **System Module**: Vector utilities for positioning

## Key Algorithms

**Mine Generation**
- Random placement with configurable mine count
- Ensures even distribution across the board

**Recursive Reveal**
- Flood-fill algorithm for revealing connected safe cells
- Automatically reveals cells with no adjacent mines
- Stops at numbered cells

**Win Detection**
- Tracks revealed safe cells
- Victory when all non-mine cells are revealed

## Development

### Built With

- **Language**: C++11
- **Graphics Library**: SFML 2.5+
- **IDE**: Visual Studio 2022
- **Compiler**: MSVC (Microsoft Visual C++)

### What I Learned

- Game development with SFML graphics library
- Event-driven programming and user input handling
- Recursive algorithms (flood-fill for cell revealing)
- Object-oriented design with C++ classes
- Working with 2D arrays and grid-based systems
- Sprite rendering and texture management
- File I/O for configuration loading
- Resource management in C++

## Future Enhancements

- [ ] Multiple difficulty presets (Easy, Medium, Hard)
- [ ] In-game timer
- [ ] Move counter
- [ ] High score system
- [ ] Sound effects
- [ ] Animations for revealing cells
- [ ] First-click safety guarantee
- [ ] Hint system
- [ ] Save/load game state

## Troubleshooting

### Common Issues

**SFML DLLs Not Found**
- Ensure SFML DLLs are in the same directory as the `.exe`
- Or add `SFML\bin` to your system PATH

**Linker Errors**
- Verify SFML library paths in project properties
- Ensure you're using matching SFML version for your compiler
- Check Debug/Release configurations match library types

**Images Not Loading**
- Verify `images/` folder is in the working directory
- Check that all sprite files exist
- Ensure working directory is set correctly in project settings

**Config File Not Found**
- Make sure `config.cfg` is in the same directory as the executable
- Check file format matches expected format

## Contributing

This is a personal educational project, but suggestions and feedback are welcome!

## License

This project was created for educational purposes.

## Acknowledgments

- SFML Documentation and Community
- Classic Minesweeper by Microsoft
- University programming coursework

## Contact

Luis B - [GitHub](https://github.com/Luis-B97)

---

**Note**: This project demonstrates C++ programming skills, game development concepts, object-oriented design, and working with external graphics libraries like SFML.
