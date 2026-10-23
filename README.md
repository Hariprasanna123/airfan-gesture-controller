
# AirFan – Gesture-Based Intelligent Fan Controller

## Project overview

AirFan is a gesture-controlled fan concept. This public website demonstrates the working principle using a laptop webcam, MediaPipe hand landmark detection, JavaScript and an animated virtual fan.

## Working principle

1. The laptop webcam captures hand movements.
2. MediaPipe detects 21 landmarks on the hand.
3. JavaScript estimates the number of extended fingers.
4. The detected gesture maps to a fan speed level.
5. The virtual ESP32 panel represents the controller command.
6. The simulated fan animation changes according to the selected level.

## Gesture mapping

| Gesture | Fan level | Display output |
|---|---:|---:|
| Fist | 0 - OFF | 0% |
| 1 finger | 1 | 20% |
| 2 fingers | 2 | 40% |
| 3 fingers | 3 | 60% |
| 4 fingers | 4 | 80% |
| 5 fingers | 5 | 100% |

The percentage is illustrative and does not represent measured fan RPM.

## Technologies used

- HTML
- CSS
- JavaScript
- MediaPipe Tasks Vision
- Browser webcam API
- GitHub Pages

## Run locally

1. Open the project folder in a terminal.
2. Run `py -m http.server 8000`.
3. Open `http://localhost:8000` in Chrome.
4. Allow webcam permission and click Start webcam.

## Important note

This website is a software-only simulation. It does not control a physical ESP32 or fan. The physical implementation would require an ESP32 and a suitable motor driver.

## Viva explanation

The laptop webcam captures hand gestures in real time. MediaPipe detects hand landmarks, and JavaScript classifies the finger pattern. The system maps the gesture to a fan speed level and displays the corresponding virtual controller command. The animated fan demonstrates the proposed response.
