🐍 Nokia Snake Game - Gesture Control
Python OpenCV MediaPipe License: MIT

Created by Chinmay Sharma

A classic Nokia Snake game controlled by hand gestures via webcam using MediaPipe and OpenCV. Experience the nostalgia of Nokia Snake with modern AI-powered gesture recognition!

Features
🎮 Classic Nokia Snake Game
Authentic Nokia-style graphics with green monochrome theme
Grid-based movement with rectangular snake segments
Growing snake mechanics - snake grows when eating fruit
Collision detection - game ends when hitting walls or self
Score tracking - earn points by eating fruit
Smooth animations with particle effects
👋 Hand Gesture Controls
MediaPipe hand tracking for real-time gesture recognition
Swipe gestures - move hand up/down/left/right to control snake direction
Pinch gesture - bring thumb and index finger together for speed boost
Face detection - shows your face in the gesture window
Visual feedback - see hand landmarks and current direction
🪟 Dual Window Interface
Game Window - Classic Nokia Snake gameplay
Gesture Window - Live webcam feed with hand tracking visualization
Quick Start
1. Install Dependencies
Run the setup script to automatically install all required packages:

python setup.py
Or install manually:

pip install -r requirements.txt
2. Run the Game
python main.py
Requirements
Python 3.7+
Webcam (built-in or external)
Required packages:
opencv-python >= 4.8.0
mediapipe >= 0.10.0
numpy >= 1.24.0
pygame >= 2.4.0
Controls
Hand Gestures
Gesture	Action
Swipe Up	Move snake up
Swipe Down	Move snake down
Swipe Left	Move snake left
Swipe Right	Move snake right
Pinch (thumb + index)	Speed boost
Game Controls
ESC - Quit game
Show UP gesture when game over - Restart game
Q in gesture window - Quit
Game Mechanics
Snake Behavior
Snake moves continuously in the current direction
Cannot move directly backward (prevents instant death)
Speed increases when pinch gesture is detected
Snake grows by one segment when eating fruit
Scoring
+10 points per fruit eaten
Score displayed in top-left corner
Final score shown on game over screen
Game Over Conditions
Snake hits the wall boundaries
Snake collides with its own body
Show UP gesture to restart
File Structure
snake_game/
├── main.py                 # Main game entry point
├── snake_game.py          # Nokia Snake game implementation
├── gesture_controller.py  # Hand gesture recognition
├── setup.py              # Automatic dependency installer
├── requirements.txt      # Python package dependencies
└── README.md            # This file
Technical Details
Game Engine
Pygame for game graphics and window management
Grid-based movement (20x20 pixel grid cells)
60 FPS display refresh rate
Variable game speed (8-15 FPS based on difficulty)
Computer Vision
MediaPipe Hands for hand landmark detection
MediaPipe Face Detection for face tracking
OpenCV for video capture and processing
Real-time gesture analysis with movement thresholds
Architecture
Threaded design - game and gesture detection run in parallel
Modular code - separate classes for game logic and gesture control
Event-driven - gestures trigger game state changes
Troubleshooting
Camera Issues
Error: Could not open webcam
Ensure webcam is connected and not used by other applications
Try changing camera index in cv2.VideoCapture(0) to 1 or 2
Check camera permissions in your OS settings
Package Installation Issues
Failed to install package
Update pip: python -m pip install --upgrade pip
Install packages individually: pip install opencv-python
Use virtual environment to avoid conflicts
Performance Issues
Low FPS: Close other applications using the camera
Gesture lag: Ensure good lighting and clear hand visibility
Game stuttering: Lower the game resolution in snake_game.py
Customization
Adjust Gesture Sensitivity
In gesture_controller.py, modify:

self.gesture_threshold = 0.05  # Lower = more sensitive
Change Game Speed
In snake_game.py, modify:

self.base_speed = 8      # Normal speed (FPS)
self.boost_speed = 15    # Boost speed (FPS)
Modify Colors
In snake_game.py, change color constants:

self.NOKIA_GREEN = (155, 188, 15)  # Snake body color
self.LIGHT_GREEN = (204, 255, 51)  # Snake head color
Development
Adding New Gestures
Extend detect_gestures() in gesture_controller.py
Add gesture recognition logic using MediaPipe landmarks
Return new gesture type in the function
Handle new gesture in main.py game loop
Modifying Game Mechanics
Edit game logic in snake_game.py
Add new features to the SnakeGame class
Update the drawing methods for visual changes
