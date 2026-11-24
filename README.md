# Whistle to Keys

A zero-dependency, browser-based live pitch tuner and melody translator built by [Voltage & Wave](https://voltageandwave.co.uk). Whistle, hum, or sing a musical phrase into your microphone and immediately see it mapped onto a cropped, purpose-built keyboard snapshot with scale inference and step-by-step playback.

---

## Features

* **Real-Time YIN Pitch Detection:** Uses a custom Web Audio API time-domain YIN autocorrelation engine with parabolic interpolation and sub-octave protection to lock onto whistled or sung pitches (`85 Hz – 3200 Hz`) with minimal latency.
* **Live Cents Deviation Tuner:** Visualises pitch accuracy (`-50c` to `+50c`), signal clarity, and real-time key illumination without needing to record first (`LIVE TUNER` mode).
* **Intelligent Note Segmentation:** Combines configurable hold gates (`65ms`, `90ms`, `135ms`), pitch hysteresis (`±52 cents`) to absorb natural vibrato, and vocal envelope dip detection to separate repeated syllables cleanly.
* **Octave Transposition:** Automatically shifts high whistled melodies down into playable registers (`0 OCT`, `-1 OCT` Synth Lead, or `-2 OCT` Bassline).
* **Cropped Snapshot Keyboard & Bird's-Eye Context:**
  * **Bird's-Eye Overview:** Displays a full `61-key` or `88-key` miniature register map with a glowing viewport frame showing where your melody sits.
  * **Auto-Cropped Keybed:** Renders only the exact span of ivory and ebony keys needed for your captured melody, highlighting root notes and scale degrees (`R`, `b3`, `4`, `5`, etc.).
* **Built-In Warm Synth & Step Sequencer:** Audition individual keys, step through notes manually (`SPACE` / arrow keys), or play back the entire translated phrase using a dual-oscillator low-pass Web Audio synthesiser.

---

## Getting Started

Because the application is built as a single self-contained `index.html` file with zero build steps or external package dependencies, you can run it locally or host it anywhere:

### Local Development
> **Note:** Modern browsers require a secure context (`https://` or `localhost`) to grant microphone access via `navigator.mediaDevices.getUserMedia()`. Opening `index.html` directly via `file://` may block microphone permissions.

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/vw-whistle-keys.git
   cd vw-whistle-keys
   ```
2. Serve the folder over `localhost` using Python, Node, or VS Code Live Server:
   ```bash
   # Using Python 3
   python3 -m http.server 8080
   ```
3. Open `http://localhost:8080` in your browser and allow microphone access when prompted.

### Deployment
Drop `index.html` directly into any static host (GitHub Pages, Netlify, Cloudflare Pages, or a subdirectory on `voltageandwave.co.uk`).

---

## Keyboard Shortcuts

| Key | Action |
| :--- | :--- |
| `Space` / `→` | Advance to the next step in the sequence |
| `←` | Return to the previous step |
| `R` | Reset sequence back to Step 1 |

---

## Licence & Attribution

&copy; 2026 [Voltage & Wave](https://voltageandwave.co.uk) &amp; **José Velázquez**. All rights reserved.
