# 🎵 Songbook Ultra

> A futuristic, all-in-one music composer, chord reference, and song learning app — built as a single HTML file with no dependencies except the browser.

![Songbook Ultra](https://img.shields.io/badge/version-2.0.0-a78bfa?style=for-the-badge)
![HTML](https://img.shields.io/badge/HTML-single--file-f59e0b?style=for-the-badge&logo=html5)
![Web Audio API](https://img.shields.io/badge/Web_Audio_API-built--in-67e8f9?style=for-the-badge)
![Claude AI](https://img.shields.io/badge/Claude_AI-optional-a78bfa?style=for-the-badge)
![No backend](https://img.shields.io/badge/backend-none-6ee7b7?style=for-the-badge)

---

## 🌌 Overview

**Songbook Ultra** is a browser-based music app that lets you compose songs, learn to play guitar and piano, detect chords from your microphone, record yourself over a backing track, and practice full songs with lyrics and chords — all in one self-contained HTML file with a futuristic universe / constellation visual design. Connect your own Anthropic API key and Claude AI takes over chord generation, lyric writing, and song inspiration throughout the app — everything still works without one, just with the built-in rule-based generators instead.

Built by **Carla Mateus** as part of her portfolio and AI Operations studies at Long Beach City College.

---

## ✨ Features

### 🎼 Sheet View
- Write songs with chords above lyrics — exactly like a real chord book
- Type chord names directly above lyric lines with live autocomplete
- Typed chords auto-generate guitar diagrams in the chord strip
- Songcraft-style guitar chord diagrams with X/O string indicators, voicing navigation (◀ 1 of 3 ▶), and Play button per chord
- Click any chord to play it and pop open an enlarged, easy-to-read chord diagram
- Drag and drop sections to reorder
- Transpose up/down by semitone
- "New Song" opens a full setup modal — title, instrument (piano/guitar), key, BPM, capo, genre, difficulty, plus an inspiration box where Claude (or the built-in mood heuristic) suggests a key/BPM/style/starter chords, or you can copy the structure of a built-in song as a starting point
- Piano instrument mode shows a mini interactive keyboard strip above the chord strip instead of guitar diagrams
- "Delete Chord" in the top bar for the last chord you clicked
- Export as plain text, MIDI-JSON, or real audio (WAV / MP3 / M4A — rendered with your selected instrument and tempo)
- Chord chips dragged in from the Writing Partner tab drop directly onto any lyric line
- Click any chord token for a rich preview popup — diagram, notes, tip, insert-again/remove — positioned next to the chord and auto-dismissing

### ✍️ Writing Partner
- Right-panel tab: describe a mood ("sad rain", "epic battle", "summer love") and get live chord suggestion chips, debounced as you type
- Key/scale selectors filter suggestions to stay in key, with an optional "keep notes in scale" guard that warns before adding an out-of-scale chord
- "Generate progression" builds a 4–8 chord progression from the mood (via Claude when connected, a curated mood→progression table otherwise), shown with roman-numeral analysis, reshuffle, and one-click "add all to sheet"
- "Chords that fit" — a function-color-coded grid (tonic/subdominant/dominant) of chords that work in the current key, click to hear or drag onto the sheet
- Every chord chip is draggable straight onto a Sheet lyric line

### 🎹 Piano Page
- **Chord Chart** — full 12-root × 5-type reference grid (like OKTAV) with interactive mini piano keyboards showing highlighted chord notes in red
- **Interactive Keyboard** — 3-octave playable keyboard with chord highlighting, note detection, and "Add to sheet" button

### 🎤 Listen Mode
- Microphone-based chord detection — works for guitar, piano, or anything else played near the mic
- YIN pitch detection plus chroma (pitch-class) template matching so it can recognize real multi-note chords, not just a single dominant string
- Confidence meter and a running history of detected chords

### ⏺ Recording Studio
- Record yourself singing or playing over the backing track (or just capture raw mic audio)
- Optionally auto-starts/stops the chord + drum playback while recording, mixed live into the take
- Session take list with playback, download, and delete per take

### 🎸 Classic Guitar Page
- Interactive fretboard with realistic wood texture, logarithmic fret spacing, wound/plain string colors
- Click frets to place finger dots with note names inside
- Chord library browser with root + type selectors
- Scale overlay (major, minor, pentatonic, blues, Dorian)
- Capo support with visual capo bar
- Strum controls with direction and speed

### 📖 Learn Page
- Chord charts and lyrics for 11 built-in songs, section by section (intro, verses, choruses, bridges, outros)
- Follow-along playback — current line and chord highlight automatically
- Chord teacher panel — click any chord to see diagram, notes, and fingering tip
- Practice mode — cycle through each chord with mastery tracking
- Strumming pattern display with animated arrows
- YouTube tutorial video embed (How to Play + Official Music Video) per song
- Section jump chips, practice loops, live transpose controls

### 🥁 Drum Machine
- 6 tracks: Kick, Snare, Hi-Hat, Clap, Tom, Perc
- 16-step sequencer with color-coded glowing steps
- 6 preset patterns: Basic, Reggae, Bossa Nova, Jazz, Hip-Hop, Latin
- Randomize button
- BPM control

### 🎵 Piano Roll
- Draw melodies on a grid (each cell = 1 eighth note)
- 36-note range (C3 to B5), 2–16 bars
- Scale highlighting — shows which notes are in your chosen key
- Playback with step cursor

### ⏱ Metronome
- Large BPM display with slider
- Time signatures: 4/4, 3/4, 6/8, 2/4
- Animated beat dots (downbeat in cyan, other beats in purple)
- **Tap tempo** — tap a button in rhythm to auto-detect BPM

### 🔍 Song Detector
- Slide-up panel with live spectrum visualizer
- Real-time instrument detection (Guitar / Piano / Bass / Drums) with animated confidence meters
- Live chord detection from microphone (same chroma-based matching as Listen Mode)
- Song matching — weights recently-played chords higher than ones played once early on, and checks that the matched chords appear in the same order the song actually uses them, not just that the same chords occur somewhere
- Match cards explain *why* they matched ("detected G, B, C, Cm — 4/4 chords present") and glow green/amber/purple by confidence tier
- "Send to Writing Partner" hands the detected progression straight to the Writing Partner tab to keep building on it

### 🔧 Tools Page
- **Visual Tuner** — real YIN pitch detection, semicircular needle gauge, note + cents readout, selectable reference pitch (432–444 Hz), guitar string reference row
- **Beat Meter** — a dedicated tap-tempo tool with a big pulse button, consistency meter, tap-interval history bars, tempo-name labels (Largo → Prestissimo), and nearby known-song BPM matches
- **Record Song** — in-browser mic recorder (MediaRecorder) with a live waveform, playback/download/discard, and a running list of your last 5 takes
- **Advanced Tools** — chord progression analyzer (key guess, roman numerals, emotional character, matching songs), scale finder (type a few notes, see which scales/keys fit), chord substitution suggestions (tritone sub, relative/parallel major-minor), and an interactive circle of fifths that sets the app's global key

### 📂 File Import
- Drag-and-drop import modal
- Supports: `.txt`, `.json`, `.mid/.midi`, `.musicxml/.xml`, `.cho/.chordpro`, `.rtf`, and audio files (`.mp3`, `.wav`, `.m4a` — chords are detected from the audio, not transcribed as lyrics)
- Auto-detects title, artist, sections, chords, and lyrics
- Preview before adding to library
- Load directly into Sheet or Learn view

### 📲 Installable App
- Works as a Progressive Web App when served over `https://` (not when just double-clicked as a local file) — installable to your desktop or phone home screen with its own icon and window

### ✦ Claude AI Integration (optional)
- "Connect Claude" in the top nav opens a login modal — paste your own [Anthropic API key](https://console.anthropic.com/settings/keys), pick a model (Sonnet 5 / Haiku 4.5 / Opus 5), and it's verified with a live test call before being saved
- **Bring-your-own-key, no backend**: the key lives only in your browser's `localStorage` and every request goes straight from your browser to `api.anthropic.com` — Songbook Ultra has no server and never sees or stores your key
- Once connected, Claude powers: mood-based chord progression generation (with a one-sentence explanation and a playing tip), a "✦ complete with Claude" button on every lyric line, and richer AI suggestions in the New Song modal's inspiration box (title ideas, key/BPM/style, starter chords, a lyric-starter line)
- Every AI feature has a built-in non-AI fallback — nothing stops working if you never connect a key, or if a request fails

---

## 🎵 Built-in Songs

| Song | Artist | Key | Difficulty |
|------|--------|-----|------------|
| Creep | Radiohead | G | Beginner |
| Wonderwall | Oasis | F#m (capo 2) | Beginner |
| Hotel California | Eagles | Bm | Intermediate |
| Blackbird | The Beatles | G | Intermediate |
| No Woman No Cry | Bob Marley | C | Beginner |
| Let Her Go | Passenger | G | Beginner |
| Mad World | Gary Jules | Fm | Beginner |
| House of the Rising Sun | The Animals | Am | Intermediate |
| Knockin' on Heaven's Door | Bob Dylan | G | Beginner |
| La Bamba | Ritchie Valens | C | Beginner |
| Stand By Me | Ben E. King | A | Beginner |

*(A few extra songs — like "More Than Words" — are available as quick-load samples on the Sheet page, but don't yet have the full Learn-page treatment: lyrics, tutorial video, and strumming pattern.)*

---

## 🔊 Instrument Sounds

All sounds are synthesized entirely in the browser using the **Web Audio API** — no audio samples, no external files.

| Instrument | Synthesis Method |
|------------|-----------------|
| 🎹 Grand Piano | 12-partial additive synthesis with inharmonicity, hammer noise, stereo panning |
| 🎸 Classical Guitar | Extended Karplus-Strong with nylon pluck character, body resonance filters |
| 🪕 Acoustic Guitar | Karplus-Strong with steel string brightness, presence boost |
| ⚡ Electric Guitar | Dual sawtooth + asymmetric waveshaper distortion, cabinet simulation |
| 🎷 Hammond Organ | 9 drawbar partials (sine waves), Leslie rotary LFO tremolo, key click |
| 🎻 Strings | 5-voice ensemble with slow bow attack, vibrato LFO, body resonance |
| 🔔 Bell | Inharmonic partials using real acoustic bell ratios |
| 🎵 Electric Bass | Sawtooth + sine, Moog-style resonant filter envelope, compressor |

Drums (Kick, Snare, Hi-Hat, Clap, Tom, Perc) all use separate physical models — not samples.

---

## 🚀 Getting Started

### Option 1 — Open directly in browser
1. Download `song-composer.html`
2. Double-click the file
3. Opens instantly in your browser — no install needed
4. Note: microphone-based features work fine this way, but YouTube tutorial embeds and "Install as app" require the page to be served over `https://` (see Option 2 or just use the hosted GitHub Pages link)

### Option 2 — VS Code + Live Server (recommended for development)
1. Install [VS Code](https://code.visualstudio.com/)
2. Install the **Live Server** extension by Ritwick Dey
3. Create a folder (e.g. `C:\Users\yourname\songbook`)
4. Put `song-composer.html` inside that folder
5. Open the folder in VS Code: **File → Open Folder**
6. Click the file, then click **Go Live** in the bottom right corner
7. Your browser opens with auto-refresh on every save

### Requirements
- Any modern browser (Chrome, Edge, Firefox, Safari)
- Microphone access — optional, only needed for Listen Mode, Recording Studio, Song Detector, and the Tools page's Tuner/Recorder
- Internet connection — optional, only needed for YouTube tutorial videos, richer chord detection (Tonal.js), and Claude AI features
- Anthropic API key — optional, only needed to unlock Claude AI-powered chord generation, lyric writing, and song suggestions (get one free at [console.anthropic.com](https://console.anthropic.com/settings/keys)); everything else works with zero setup

---

## 🎨 Design

The app uses a **Universe / Constellation** visual theme:

- **Animated star field** — 220 twinkling stars with nebula glows rendered on a canvas background
- **Glass morphism panels** — all UI surfaces use `backdrop-filter: blur` for a holographic floating look
- **Aurora waveform** — the visualizer bar uses a gradient stroke from purple → cyan → pink → amber
- **Cosmic color palette** — deep space black backgrounds, nebula purple accents, pulsar amber for chords, cyan for scale notes
- **Constellation glow effects** — active elements pulse with matching colored box-shadows

---

## 🗂 Project Structure

```
song-composer.html      ← The entire app — HTML + CSS + JS in one file
index.html              ← Redirects to song-composer.html (clean GitHub Pages root URL)
README.md               ← This file
```

Everything is self-contained. No build step, no npm, no framework.

---

## 🧠 Technical Details

| Feature | Technology |
|---------|-----------|
| Audio synthesis | Web Audio API (OscillatorNode, BiquadFilterNode, WaveShaperNode, DynamicsCompressorNode, StereoPannerNode) |
| Pitch/chord detection | YIN algorithm + chroma (pitch-class profile) template matching |
| Chord recognition | Custom interval matching + Tonal.js (optional CDN) |
| Recording | MediaRecorder API, mixed live with the app's own audio graph |
| Guitar diagrams | HTML5 Canvas |
| Piano keyboard | HTML5 Canvas + DOM |
| Waveform visualizer | HTML5 Canvas with requestAnimationFrame |
| Spectrum analyzer | AnalyserNode FFT |
| Star field | HTML5 Canvas animation |
| File parsing | FileReader API, DOMParser (XML), ArrayBuffer (MIDI/audio) |
| YouTube videos | iframe embed |
| Local storage | Save/load songs between sessions |
| Drag and drop | HTML5 Drag and Drop API |
| Installability | Web App Manifest + runtime-generated icon (no separate files) |
| AI features | Direct browser → Anthropic Messages API calls (`anthropic-dangerous-direct-browser-calls`), bring-your-own-key, no backend |

---

## 📋 Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `Enter` / `Tab` | Confirm typed chord in chord input |
| `Space` | Confirm chord and move to next |
| `↑` / `↓` | Navigate chord suggestions |
| `Escape` | Cancel chord input |
| Right-click chord token | Remove chord |

---

## 🔧 Known Limitations

- Microphone-based chord detection works best in a quiet environment. It can recognize real multi-note chords via chroma matching, but a monophonic pitch tracker still underlies part of the pipeline, so very complex or heavily distorted voicings may resolve to a simpler match
- MIDI file import extracts note data but doesn't reconstruct full chord charts — manual editing may be needed
- Guitar Pro (`.gpx`/`.gp5`) parsing is best-effort only (the format is proprietary/binary) — re-exporting to MusicXML or text from Guitar Pro first will import more reliably
- YouTube embeds and the "Install as app" prompt require the page to be served over `https://` — opening the file directly (`file://`) will show a player error / no install option, which is a browser restriction, not a bug
- True offline caching isn't possible in a single HTML file under current browser security rules (a service worker's script has to be a real fetchable file); the manifest/install still work without it

---

## 📌 Roadmap Ideas

- [x] Chord progression AI using Claude API
- [ ] Cloud save / sync across devices
- [ ] More songs (50+ target)
- [ ] Custom tuning support (Drop D, Open G, DADGAD)
- [ ] Export to PDF chord sheet
- [ ] Mobile touch support for the guitar fretboard
- [ ] Collaborative editing via WebSockets
- [ ] Wire Claude into chord explanations (function ready, not yet on a button) and full song-idea generation

---

## 👩‍💻 Author

**Carla Mateus**
- GitHub: [@Gallozita02](https://github.com/Gallozita02)
- FreeCodeCamp: [freecodecamp.org/carlamateus](https://freecodecamp.org/carlamateus)
- Student at Long Beach City College — AS in Computer Technology (AI Operations & Data Analytics)

---

## 📄 License

This project is for educational and portfolio purposes.
Song lyrics and chord arrangements are used for learning — all original compositions belong to their respective artists and publishers.

---

*Built with ♪ and Web Audio API — no frameworks were harmed in the making of this app.*
