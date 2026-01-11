# Gesture Controlled Holographic Interface
AIR CANVAS is a web-based, real-time gesture-controlled drawing system that allows users to draw, erase, and move digital content in mid-air using only their hand gestures captured through a webcam.
The project simulates a futuristic holographic interface, inspired by sci-fi HUD (Heads-Up Display) systems, without requiring any external hardware like gloves or sensors.

The system is built using HTML, CSS, JavaScript, and MediaPipe Hands, making it lightweight, browser-compatible, and fully interactive.

  What the Project Does

  AIR CANVAS transforms your hand movements into digital actions:

  Draw on a virtual grid using a pinch gesture

  Erase drawn blocks using a second-hand pinch

  Move/Pan the entire canvas by holding a fist

  Recognize gestures intelligently with delay-based confirmation to avoid accidental actions

  Display a futuristic HUD interface with real-time status, modes, and visual feedback

  All interactions happen in real time, creating the illusion of drawing in the air.

Core Technologies Used
Frontend

  HTML5 – Structure and canvas rendering

  CSS3 – Futuristic HUD styling, overlays, animations

  JavaScript – Gesture logic, state management, rendering engine

Computer Vision & AI

MediaPipe Hands

  Tracks two hands simultaneously
  Enables gesture recognition (pinch, fist)
  System Architecture (How It Works)
1. Camera & Hand Tracking

  Webcam feed is captured in real time

  MediaPipe detects hand landmarks (finger tips, joints, palm points)

  The video feed is mirrored for natural interaction

2. Gesture Recognition Logic

  The system identifies gestures using landmark distances and positions:

  Gesture	Detection Logic	Action
  Pinch	Distance between thumb & index finger < threshold	Draw / Erase
  Fist	Fingers curled outward	Move canvasTwo Hands	Second hand detected	Eraser mode

  Timers are used so gestures must be held before activation, preventing accidental triggers.

3. Drawing Engine (Grid-Based Canvas)

  The canvas is divided into virtual grid blocks

  Each drawn block is stored in a Map data structure

  This ensures:

  Fast lookups (O(1))

  No duplicate blocks

  Clean erasing and movement

  Each block is rendered as a holographic cube with:

  Transparency

  Glowing borders

  Inner tech-style cross design

4. Canvas Movement System

  When the user holds a fist for 2 seconds:

  The grid gets “locked”

  Hand movement shifts the entire canvas

  Movement is snapped to grid size to avoid visual distortion

5. Smoothing & Stability

  Raw hand movement is smoothed using linear interpolation (LERP)

  This reduces jitter and provides:

  Stable drawing

  Precise control

  Natural hand feel

6. HUD & Visual Feedback

  The interface provides continuous feedback:

  Current mode (Drawing, Erasing, Moving, Idle)

  Charging animations for gestures

  Circular loaders around the hand

  Grid portals near the cursor

  Status messages and debug logs
