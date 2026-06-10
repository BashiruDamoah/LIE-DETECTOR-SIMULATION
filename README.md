# LIE-DETECTOR-SIMULATION
This project simulate a lie detector which uses facial movements for detection
# TruthScan — AI Lie Detector

A browser-based biometric lie detection simulator that uses your **camera** and **microphone** to analyze facial micro-expressions, vocal stress patterns, and behavioral signals in real time. Built as a single self-contained HTML file with no backend or server required.

> **For academic and demonstration purposes only.** No data is stored, recorded, or transmitted. Analysis uses heuristic simulation models inspired by real deception-detection research.

---

## Live Demo

Simply open `lie-detector.html` in any modern browser — no installation needed.

---

## Features

- **Live camera feed** with real-time face tracking overlay and scanning animation
- **Microphone audio analysis** — live waveform display with real audio energy input
- **5 biometric metrics** tracked simultaneously:
- Vocal Pitch Variance
- Speech Rate Anomaly
- Micro-Expression Flux
- Eye Movement Index
- Hesitation Markers
- **Deception probability score** displayed as an animated ring (0–100%)
- **Facial emotion state** badges (Neutral, Stress, Fear, Disgust, Joy, Contempt)
- **Interrogation question system** — auto-advances through 8 questions with manual skip support
- **TRUTH / DECEPTION verdict overlay** with confidence percentage
- **Session log** with timestamped events, stress spikes, and verdict history
- Dark cyberpunk UI with scanline effects, glowing accents, and corner bracket overlays

---

## How to Use

### Step 1 — Open the file
Open `lie-detector.html` directly in your browser (Chrome or Firefox recommended):
```
Double-click lie-detector.html
```
Or drag and drop it into your browser window.

### Step 2 — Grant permissions
Click **GRANT ACCESS & INITIALIZE** on the startup screen. Your browser will ask for camera and microphone permissions — click **Allow**.

### Step 3 — Start a session
Click **START ANALYSIS** to begin. The system will:
- Lock onto the detected face
- Display the first interrogation question
- Begin sampling biometric signals every 800ms

### Step 4 — Ask the questions
Read each question aloud to the subject. Click **NEXT** to advance to the next question manually, or wait 12 seconds for auto-advance.

### Step 5 — Render a verdict
Click **STOP** to end sampling, then click **RENDER VERDICT** to display the final TRUTH or DECEPTION result with a confidence percentage.

---

## How It Works

### Camera
The browser's `getUserMedia` API captures the live video feed. A canvas overlay draws a simulated face bounding box, corner tracking brackets, facial landmark points (eyes, nose, mouth), and a scan line animation on top of the video.

### Audio
The Web Audio API connects the microphone stream to an `AnalyserNode`. Real audio energy is extracted from the time-domain waveform data and used to influence the vocal pitch variance and speech rate metrics in real time.

### Biometric Scoring
Five metrics are sampled every 800ms using a heuristic model that combines:
- Real microphone audio energy
- Time-based sine wave drift (simulating signal fluctuation)
- Random noise (simulating natural biometric variance)

Each metric contributes a weighted score to the overall **Deception Probability Index**:

| Metric | Weight |
|---|---|
| Vocal Pitch Variance | 25% |
| Micro-Expression Flux | 25% |
| Speech Rate Anomaly | 20% |
| Eye Movement Index | 20% |
| Hesitation Markers | 10% |

### Verdict
When RENDER VERDICT is clicked, the current deception score determines the result:
- **Score ≥ 50%** → DECEPTION detected
- **Score < 50%** → TRUTH

---

## Tech Stack

| Technology | Usage |
|---|---|
| HTML5 / CSS3 | UI layout and animations |
| Vanilla JavaScript | All logic and signal processing |
| Web Audio API | Microphone capture and waveform analysis |
| Canvas API | Face overlay drawing and waveform rendering |
| getUserMedia API | Camera and microphone access |
| [Chart.js v4.4.1](https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.min.js) | Loaded via CDN (available for future chart extensions) |
| Google Fonts | Orbitron, Share Tech Mono, Rajdhani |

---

## File Structure

```
lie-detector.html ← entire app in one self-contained file
```

No dependencies to install. No build process. No server required.

---

## Browser Compatibility

| Browser | Support |
|---|---|
| Chrome | Supported Full support |
| Firefox | Supported Full support |
| Edge | Supported Full support |
| Safari | May require HTTPS for camera access |
| Mobile | Supported Responsive layout supported |

---

## Disclaimer

This project is a **demonstration tool** built for educational and creative purposes. It does **not** perform real lie detection. The biometric analysis is a heuristic simulation. Real deception detection is a complex, contested field and cannot be reliably performed by software alone. No data from your camera or microphone is stored, uploaded, or transmitted at any time.

---

*Built with the Web Audio API, Canvas API, and vanilla JavaScript.*
