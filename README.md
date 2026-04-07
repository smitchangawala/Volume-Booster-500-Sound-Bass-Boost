  # 🔊 Sound Booster — Chrome Extension

**Boost audio up to 500% on any website** with built-in EQ controls, presets, and a real-time visualizer.

> Tired of low-volume videos, quiet podcasts, or barely audible streams? Sound Booster amplifies any tab's audio beyond the browser's default limit — cleanly and without distortion.

---

## ✨ Features

- 🔈 **Volume Boost up to 500%** — go way beyond the default maximum
- 🎛️ **Bass & Treble EQ** — fine-tune low and high frequencies (-10 to +10 dB)
- 🎧 **4 Smart Presets** — General, Speech, Music, Movie — each with tuned compressor + EQ settings
- 📊 **Real-Time Visualizer** — see your audio frequency bars respond live
- 🧱 **Brick-Wall Limiter** — prevents distortion and clipping even at high volumes
- 💾 **Persistent Settings** — your preferences are saved automatically and restored on next use
- 🌐 **Works on Any Website** — YouTube, Spotify, Netflix, podcasts, video calls — everything
- 🎯 **Dynamic Media Detection** — automatically detects new audio/video elements (YouTube SPA, dynamically loaded players)
- ⚡ **Lightweight** — no bloat, no analytics, no background processes when idle

---

## 🛠️ Tech Stack

- **Manifest V3** — latest Chrome extension standard
- **Web Audio API** — professional-grade audio processing chain
- **Vanilla JS/CSS** — zero dependencies, fast and lightweight

### Audio Processing Chain

```
MediaElementSource
  → GainNode (non-linear 0–500% boost)
  → DynamicsCompressor (preset-dependent)
  → BiquadFilter (Bass EQ — lowshelf 200 Hz)
  → BiquadFilter (Treble EQ — highshelf 3 kHz)
  → DynamicsCompressor (Limiter — ratio 20, threshold -2 dB)
  → AnalyserNode (visualizer)
  → AudioContext.destination
```

---

## 📦 Installation

### From Chrome Web Store
*(Coming soon)*

### Manual Install (Developer Mode)

1. Download or clone this repository
   ```bash
   git clone https://github.com/smitchangawala/Volume-Booster-500-Sound-Bass-Boost.git
   ```
2. Open Chrome and go to `chrome://extensions/`
3. Enable **Developer mode** (toggle in top-right)
4. Click **"Load unpacked"**
5. Select the `sound-booster` folder
6. Click the 🔊 icon in your toolbar — done!

---

## 🎮 How to Use

1. Open any website with audio or video
2. Click the **Sound Booster** icon in your browser toolbar
3. Toggle the switch **ON**
4. Drag the **volume slider** to boost (up to 500%)
5. Choose a **preset** or manually adjust **Bass/Treble**
6. Watch the **visualizer** respond in real time

---

## 🎧 Presets

| Preset |  Best For |
|--------|----------|
| 🎧 General | Everyday browsing |
| 🎙️ Speech | Podcasts, lectures, calls |
| 🎵 Music | Songs, concerts, playlists |
| 🎬 Movie | Movies, shows, trailers |

---

## 📁 Project Structure

```
sound-booster/
├── manifest.json              # Extension manifest (V3)
├── background/
│   └── service-worker.js      # Script injection & message routing
├── content/
│   ├── audioEngine.js         # Web Audio API processing chain
│   └── content.js             # DOM scanner & MutationObserver
├── popup/
│   ├── popup.html             # Popup UI
│   ├── popup.js               # UI logic, visualizer, state
│   └── popup.css              # Dark theme styling
├── icons/
│   ├── icon16.png
│   ├── icon48.png
│   └── icon128.png
└── privacy-policy.html        # Privacy policy page
```

---

## 🔒 Privacy

Sound Booster respects your privacy completely:

- ❌ **No data collection** — zero personal information collected
- ❌ **No analytics or tracking** — no third-party services
- ❌ **No external requests** — everything runs locally
- ✅ **Local storage only** — settings saved on your device via `chrome.storage.local`

Read the full [Privacy Policy](privacy-policy.html).

---

## 🛡️ Permissions Explained

| Permission | Why It's Needed |
|------------|-----------------|
| `activeTab` | Access the current tab's audio elements |
| `scripting` | Inject the audio engine into web pages |
| `storage` | Save your volume and EQ preferences locally |
| `tabs` | Detect page navigation to re-initialize the booster |
| `<all_urls>` | Allow boosting on any website |

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the repo
2. Create your branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 👨‍💻 Author

**Smit Changawala**

- LinkedIn: [Smit Changawala](https://www.linkedin.com/in/smit-changawala-82695926b/)

---

<p align="center">Made with 💗 by <a href="https://www.linkedin.com/in/smit-changawala-82695926b/">Smit</a></p>
