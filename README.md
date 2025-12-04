![Voice AI Assistant Banner](https://media.giphy.com/media/3oEjI6SIIHBdRxXI40/giphy.gif)

# 🎙️ AI Voice Assistant — Real-Time (Ears → Brain → Mouth)

**A lightweight, privacy-first voice assistant** that listens to you, thinks locally using a Llama 3 model (via Ollama), and speaks back — all running on your machine. This notebook-based project is perfect for quick experiments, demos, and local offline assistants. ✨

---

**Table of Contents**
- **Project Overview**
- **Animated Preview**
- **Features**
- **Requirements**
- **Installation**
- **Usage**
- **Notebook Walkthrough**
- **Files**
- **Future Enhancements**
- **Contributing & License**
- **Push to GitHub**

---

**Project Overview**
- **What:** A Python Jupyter Notebook that wires up speech recognition → LLM inference (local Llama 3 via Ollama) → text-to-speech.
- **Why:** Build a private, offline-capable voice assistant prototype that you can improve and extend.
- **Who:** Great for hobbyists, researchers, and devs experimenting with local LLMs and voice UX.

**Animated Preview**
- Replace the preview below with your own recorded GIF for best presentation (use an animated GIF showing the assistant running):

![Animated Preview](https://media.giphy.com/media/3oEjI6SIIHBdRxXI40/giphy.gif)

---

**Features**
- **Listen:** Uses `SpeechRecognition` and your system microphone to capture and transcribe audio. 🎧
- **Think:** Calls Ollama (`ollama.chat`) to query a local Llama 3 model for responses. 🧠
- **Speak:** Uses `pyttsx3` for platform TTS (SAPI5 on Windows). 🗣️
- **Looping Assistant:** Always-on Listen → Think → Speak loop with graceful exit keywords.

---

**Requirements**
- **OS:** Windows / macOS / Linux (microphone support required)
- **System tools:** `Ollama` desktop app/CLI installed and running
- **Model:** `llama3` pulled locally via Ollama (`ollama pull llama3`)
- **Python packages:**
  - `SpeechRecognition`
  - `ollama`
  - `pyttsx3`
  - `pyaudio` (or install via `pipwin` on Windows if wheel issues)

---

**Installation**
- Open PowerShell and run (recommended within a venv):

```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

- If `pyaudio` fails on Windows, install `pipwin` then `pipwin install pyaudio`:

```powershell
pip install pipwin
pipwin install pyaudio
```

- Install Ollama (download from https://ollama.ai/) and pull Llama 3:

```powershell
ollama pull llama3
```

---

**Usage**
- Open the notebook `Voice_AI_Assistant.ipynb` in JupyterLab/Notebook and run cells in order.
- In the final code cell, uncomment `main()` and run it to start the assistant:

```python
main()  # start the Listen -> Think -> Speak loop
```

- Speak to the mic. Say `exit`, `stop`, or `quit` to end the session.

**Run as script (optional)**
- You can extract the notebook code into `assistant.py` and run:

```powershell
python assistant.py
```

Make sure Ollama is running and the `llama3` model is available.

---

**Notebook Walkthrough (Quick)**
- **Cell 1:** Install packages (this notebook includes an automated `pip install` step).
- **Cell 2:** Imports (`speech_recognition`, `ollama`, `pyttsx3`).
- **Cell 3:** `listen()` — captures microphone audio and transcribes via Google Web Speech.
- **Cell 4:** `think()` — sends text to `ollama.chat` (model: `llama3`).
- **Cell 5:** `speak()` — uses `pyttsx3` to speak text.
- **Cell 6:** `main()` — orchestrates the loop.

---

**Files**
- `Voice_AI_Assistant.ipynb` — main notebook with full implementation.
- `README.md` — this file (project overview & usage).
- `requirements.txt` — Python dependencies.

---

**Future Enhancements**
- **Wake-word detection:** Add an always-listening hotword (e.g., `snowboy` or `Porcupine`) to avoid full-time recording. 🔔
- **Streaming STT:** Integrate a low-latency streaming STT engine for faster responsiveness. ⚡
- **Better TTS:** Add high-quality TTS (e.g., Coqui TTS, Edge TTS, or ElevenLabs) with voice profiles. 🎙️
- **Multi-turn memory:** Add short-term memory and conversation context handling. 🧾
- **Action hooks:** Integrate calendar, email, or system-control plugins for actionable responses. 🔌
- **Web UI:** Add a small web dashboard to visualize transcripts and audio, and to replay sessions with animated waveforms. 🌐

---

**Contributing & License**
- **How to contribute:** Fork, add improvements, and send a PR. Open issues for feature requests or bugs.
- **License:** MIT — feel free to reuse and extend.

---

**Push to GitHub**
- Quick steps to push this project (PowerShell):

```powershell
# Initialize if not a git repo
git init
git add .
git commit -m "Initial: Voice AI Assistant notebook + README"
# Add your remote (replace URL below)
git remote add origin https://github.com/your-username/your-repo.git
# Push to GitHub (main branch)
git branch -M main
git push -u origin main
```

- If you already have a repo on GitHub, replace the remote URL with your repo's URL.

---

**Animated Design Tips**
- Use a short animated GIF (3–6s) showing the assistant in action — insert it at the top of the README.
- Create a small GIF using `recordmydesktop` or an online screen recorder showing the notebook running and the assistant speaking.
- Add a GitHub Action that regenerates a preview GIF or runs a short smoke test for demos.

---

If you want, I can:
- create a `requirements.txt` for you now,
- add a simple `.gitignore`,
- or prepare a lightweight `assistant.py` runner script extracted from the notebook.

Which would you like me to do next? 🚀
