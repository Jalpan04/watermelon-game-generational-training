# Watermelon Game (Suika Game) Clone with AI Autoplay

[![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org) [![Pygame](https://img.shields.io/badge/Pygame-F37626?style=flat&logo=python&logoColor=white)](https://www.pygame.org) [![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat&logo=opencv&logoColor=white)](https://opencv.org) ![GitHub repo size](https://img.shields.io/github/repo-size/Jalpan04/watermelon-game-generational-training) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A custom desktop Pygame clone of the popular **Watermelon Game (Suika Game)**, accompanied by an automated AI player agent (`learner.py`) that plays the game autonomously using Computer Vision (OpenCV) and screen control inputs (PyAutoGUI).

## Features

### 🍉 The Game: Fruity (`fruty.py`)
- **Physics Simulation**: Custom-built rigid circle physics simulating gravity, friction, collisions, and elastic merging.
- **Merge Progression**: Combine matching lower-tier fruits to upgrade them into higher-tier, larger fruits (from grapes up to the final watermelon).
- **Retro UI Layout**: Dark-themed top header showing current score, high score, and a queue displaying the upcoming fruits.
- **Drop Line Guide**: Real-time dotted guides showing where the fruit will land.

### 🤖 The AI Player: Learner (`learner.py`)
- **Real-time Screen Capture**: Captures the game window viewport dynamically using the high-performance `mss` package.
- **Fruit Preview Identification**: Analyzes dominant RGB color blocks at UI preview coordinates to classify current and upcoming fruit types.
- **Computer Vision Contours**: Uses OpenCV (`cv2`) threshold masking and contour detection to count fruits on the board.
- **Autonomous Game Loop**: Emulates mouse navigation and drop coordinates using `pyautogui`, locking onto optimal drop intervals.

## Tech Stack

- **Game Engine**: `pygame`
- **Computer Vision**: `opencv-python` (OpenCV)
- **Screen Capturing**: `mss`
- **GUI Automation**: `pyautogui`, `pygetwindow`
- **Control Listeners**: `keyboard`
- **Utilities**: `numpy`

## File Structure

```
├── fruty.py              # Main Pygame application, collision solver, and UI
├── learner.py            # AI agent loop, screen-capture analyzer, and autoplay controller
├── .gitignore            # Git ignore patterns
└── LICENSE               # MIT License
```

## Getting Started

### Prerequisites
- Python 3.8 or higher.
- Windows Operating System (required for `pygetwindow` window mapping).

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Jalpan04/watermelon-game-generational-training.git
   ```
2. Install dependencies:
   ```bash
   pip install pygame opencv-python pyautogui pygetwindow mss keyboard numpy
   ```

### Execution

- **To Play Manually**:
  ```bash
  python fruty.py
  ```
  - Move mouse horizontally to aim.
  - Click to drop the fruit.
  - Press `R` to restart on game over.

- **To Run AI Autoplay**:
  1. Open the command terminal as Administrator (needed for `keyboard` and `pyautogui` library hooks).
  2. Run the learner agent:
     ```bash
     python learner.py
     ```
  3. The agent will launch the game script automatically, detect the screen region, and start dropping fruits.
  4. Press the `ESC` key on your keyboard to terminate the autoplay agent at any time.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
