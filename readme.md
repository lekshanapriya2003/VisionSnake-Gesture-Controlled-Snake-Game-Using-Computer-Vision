# Gesture-Controlled Snake Game (Computer Vision)

## Overview

This project is a **real-time, gesture-controlled Snake Game** built using **Computer Vision**. The traditional keyboard-based controls are replaced with **hand tracking**, where the snake follows the movement of the player's **index finger** detected via a webcam.

The game integrates **OpenCV**, **cvzone**, and **MediaPipe-based hand tracking**, along with **Pygame** for sound effects, delivering an interactive and immersive experience.

---

## Key Features

- Real-time hand tracking using a webcam
- Index finger controls snake movement
- Dynamic snake growth on food consumption
- Collision detection with self-body
- Score tracking system
- Game-over and restart functionality
- Sound effects for eating food and game over

---

## Tech Stack & Libraries Used

### Programming Language

- **Python 3.8+**

### Core Libraries

- **OpenCV (cv2)** – Video capture, image processing, rendering
- **cvzone** – Simplified computer vision utilities and overlays
- **MediaPipe (via cvzone HandTrackingModule)** – Hand landmark detection
- **NumPy** – Numerical operations and array handling
- **Math** – Distance calculations
- **Random** – Random food placement
- **Pygame** – Audio playback for game sound effects

---

## Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/gesture-snake-game.git
cd gesture-snake-game
```

### 2. Create a Virtual Environment (Recommended)

```bash
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install opencv-python cvzone mediapipe numpy pygame
```

### 4. Required Assets

Make sure the following files are present in the project root:

- `Donut.png` – Food image (PNG with transparent background)
- `eat.wav` – Sound played when food is eaten
- `gameover.wav` – Sound played on collision

---

## How to Run the Game

```bash
python main.py
```

- Ensure your **webcam is enabled**
- Use your **index finger** to control the snake
- Press **R** to restart after Game Over

---

## Game Logic Explained

### Hand Tracking

- Tracks a single hand using MediaPipe
- Uses **landmark 8 (index finger tip)** as the snake head position

### Snake Movement

- Snake body is constructed using a list of points
- Distance between consecutive points determines length
- Tail trimming ensures controlled growth

### Collision Detection

- Uses `cv2.pointPolygonTest()` to detect self-collision
- On collision:
  - Game state resets
  - Score resets
  - Game-over sound is triggered

---

## Controls

| Action       | Control               |
| ------------ | --------------------- |
| Move Snake   | Index Finger Movement |
| Restart Game | `R` Key               |

---

## Project Structure

```
├── main.py
├── Donut.png
├── eat.wav
├── gameover.wav
├── README.md
```

---

## Limitations (Honest)

- Requires good lighting for accurate hand tracking
- Webcam latency may affect precision
- No difficulty scaling beyond snake length

---

## Future Enhancements

- Multiple difficulty levels
- Gesture-based restart (no keyboard)
- Obstacle-based levels
- High-score persistence
- Multiplayer hand tracking

---

## License

This project is open-source and available under the **MIT License**.



