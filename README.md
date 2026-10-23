# AirFan – Gesture-Based Intelligent Fan Controller

A public browser-based simulation using a webcam and MediaPipe Hand Landmarker. It tracks hand landmarks, estimates the number of extended fingers, maps the result to levels 0–5, and animates a virtual fan.

## Important
- Software simulation only: the virtual ESP32 panel is explanatory and does not communicate with a physical ESP32 or motor.
- Webcam access requires permission and a secure context such as HTTPS (GitHub Pages) or localhost.
- Internet access is needed to load MediaPipe JavaScript, WebAssembly and the model.
- Camera frames are processed in the browser by this page; this project does not upload or store camera footage.

## Run locally on Windows
1. Extract this ZIP.
2. Open the extracted folder in File Explorer.
3. Click the address bar, type `cmd`, and press Enter.
4. Run `py -m http.server 8000`
5. Open `http://localhost:8000` in Chrome.
6. Click **Start webcam** and allow permission. Show one hand with the full hand visible.
7. If camera/model access is unavailable, click the manual OFF/1–5 buttons to demonstrate the fan.
8. Press Ctrl+C in Command Prompt to stop the server.

## Publish publicly with GitHub Pages
1. Sign in to GitHub and create a **public repository** named `airfan-gesture-controller`.
2. Extract this ZIP on your computer.
3. In the new repository, choose **Add file → Upload files**.
4. Upload `index.html`, `README.md` and `.nojekyll` from the extracted folder (upload the files, not the ZIP).
5. Commit to the `main` branch.
6. Open **Settings → Pages**.
7. Under Build and deployment, choose **Deploy from a branch**.
8. Select branch `main`, folder `/(root)`, then click **Save**.
9. Wait for publishing. The address will be `https://YOUR-GITHUB-USERNAME.github.io/airfan-gesture-controller/`. Replace the username with your GitHub username; GitHub also shows the exact URL under Settings → Pages.

## Gesture mapping
| Extended fingers | Fan level | Display scale |
|---:|---:|---:|
| 0 (fist) | OFF / 0 | 0% |
| 1 | Level 1 | 20% |
| 2 | Level 2 | 40% |
| 3 | Level 3 | 60% |
| 4 | Level 4 | 80% |
| 5 | Level 5 | 100% |

Percentages are illustrative, not measured RPM. Finger counting is geometric and may be less reliable if the hand is sideways, partly hidden or outside the frame.

## Viva explanation
“The laptop webcam captures my hand in real time. MediaPipe identifies 21 hand landmarks. JavaScript estimates how many fingers are extended and maps that number to fan levels 0 to 5. The website displays a virtual controller command and animates the fan. This website is a software-only simulation; the physical implementation would use an ESP32 and a suitable motor driver.”
