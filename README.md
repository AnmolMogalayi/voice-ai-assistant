# 🎙️ AI Voice Assistant — Real-Time Voice AI (Ears → Brain → Mouth)

**A lightweight, privacy-first voice assistant** that listens to you, thinks locally using a Llama 3 model (via Ollama), and speaks back — all running on your machine. This notebook-based project is perfect for quick experiments, demos, and local offline assistants. ✨

---

## 📑 Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Notebook Walkthrough](#notebook-walkthrough)
- [Project Files](#project-files)
- [Future Enhancements](#future-enhancements)
- [Contributing & License](#contributing--license)

---

## 🎯 Project Overview

**What:** A Python Jupyter Notebook that wires up speech recognition → LLM inference (local Llama 3 via Ollama) → text-to-speech.

**Why:** Build a private, offline-capable voice assistant prototype that you can improve and extend.

**Who:** Great for hobbyists, researchers, and devs experimenting with local LLMs and voice UX.

---

## ✨ Features

- **🎧 Listen:** Uses `SpeechRecognition` and your system microphone to capture and transcribe audio.
- **🧠 Think:** Calls Ollama (`ollama.chat`) to query a local Llama 3 model for responses.
- **🗣️ Speak:** Uses `pyttsx3` for platform TTS (SAPI5 on Windows, NSS on macOS, eSpeak on Linux).
- **🔄 Looping Assistant:** Always-on Listen → Think → Speak loop with graceful exit keywords (`exit`, `stop`, `quit`).

---

## 📋 Requirements

- **OS:** Windows / macOS / Linux (microphone support required)
- **System tools:** `Ollama` desktop app/CLI installed and running
- **Model:** `llama3` pulled locally via Ollama (`ollama pull llama3`)
- **Python packages:**
  - `SpeechRecognition`
  - `ollama`
  - `pyttsx3`
  - `pyaudio` (or install via `pipwin` on Windows if wheel issues)

---

## 🚀 Installation

### Step 1: Clone or Download the Repository
```powershell
git clone https://github.com/AnmolMogalayi/voice-ai-assistant.git
cd voice-ai-assistant
```

### Step 2: Create Virtual Environment (Optional but Recommended)
```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

### Step 3: Install Python Dependencies
```powershell
pip install -r requirements.txt
```

### Step 4: Handle PyAudio on Windows (if needed)
If `pyaudio` fails to install, use `pipwin`:
```powershell
pip install pipwin
pipwin install pyaudio
```

### Step 5: Install Ollama & Llama 3
- Download Ollama from https://ollama.ai/
- Install and run it
- Pull the Llama 3 model:
```powershell
ollama pull llama3
```

---

## 💡 Usage

### Option 1: Run via Jupyter Notebook (Recommended for Learning)
```powershell
jupyter notebook Voice_AI_Assistant.ipynb
```
Then run cells in order and uncomment `main()` in the final cell.

### Option 2: Run as Python Script
```powershell
python assistant.py
```

### How to Use the Assistant
1. Run the script/notebook
2. Wait for "Hello, I am ready. You can start speaking."
3. Speak into your microphone
4. The assistant will transcribe, think, and respond
5. Say `exit`, `stop`, or `quit` to end the session

---

## 📖 Notebook Walkthrough

| Cell | Purpose |
|------|---------|
| 1 | **Install Packages** - Automated pip install for all dependencies |
| 2 | **Import Libraries** - `speech_recognition`, `ollama`, `pyttsx3` |
| 3 | **`listen()`** - Captures microphone audio and transcribes via Google Web Speech |
| 4 | **`think()`** - Sends text to `ollama.chat` (model: `llama3`) |
| 5 | **`speak()`** - Uses `pyttsx3` to convert text to speech |
| 6 | **`main()`** - Orchestrates the complete Listen → Think → Speak loop |

---

## 📁 Project Files

| File | Description |
|------|-------------|
| `Voice_AI_Assistant.ipynb` | Main Jupyter Notebook with full implementation and step-by-step walkthrough |
| `assistant.py` | Standalone Python script runner (can be used as a module or CLI) |
| `README.md` | Project documentation (this file) |
| `requirements.txt` | Python package dependencies |
| `.gitignore` | Git ignore rules for Python and Jupyter projects |

---

## 🔮 Future Enhancements

- **🔔 Wake-word detection:** Add always-listening hotword (e.g., `Porcupine` or `Snowboy`) to avoid full-time recording
- **⚡ Streaming STT:** Integrate low-latency streaming speech-to-text for faster responsiveness
- **🎤 Better TTS:** Add high-quality TTS engines (Coqui TTS, Edge TTS, or ElevenLabs) with voice profiles
- **🧾 Multi-turn memory:** Add conversation context and short-term memory handling
- **🔌 Action hooks:** Integrate calendar, email, or system-control plugins for actionable responses
- **🌐 Web UI:** Build a web dashboard to visualize transcripts, manage settings, and replay sessions
- **📊 Metrics:** Add logging and analytics to track assistant performance
- **🎓 Fine-tuning:** Allow custom Ollama model fine-tuning for domain-specific responses

---

## 🤝 Contributing & License

**How to contribute:**
- Fork the repository
- Create a feature branch (`git checkout -b feature/my-feature`)
- Commit changes (`git commit -m "Add my feature"`)
- Push to branch (`git push origin feature/my-feature`)
- Open a Pull Request

**License:** MIT — Feel free to reuse, modify, and distribute this project!

---

## ❓ Troubleshooting

### Issue: "No module named 'pyaudio'"
**Solution:** Use `pipwin` on Windows:
```powershell
pip install pipwin
pipwin install pyaudio
```

### Issue: "Ollama is not running"
**Solution:** Start Ollama application or run `ollama serve` in terminal

### Issue: "Model 'llama3' not found"
**Solution:** Pull the model:
```powershell
ollama pull llama3
```

### Issue: Microphone not detected
**Solution:** Check system settings and ensure microphone is enabled and configured as default input device

### Issue: Speech recognition not working
**Solution:** Ensure internet connection (Google Web Speech API requires it)

---

## 📧 Contact & Support

For issues, feature requests, or questions:
- Open an [Issue](https://github.com/AnmolMogalayi/voice-ai-assistant/issues) on GitHub
- Visit the repository: https://github.com/AnmolMogalayi/voice-ai-assistant

---

## 🙏 Acknowledgments

Built with ❤️ using:
- [SpeechRecognition](https://github.com/Uberi/speech_recognition) - Speech-to-Text
- [Ollama](https://ollama.ai/) - Local LLM inference
- [pyttsx3](https://github.com/nateshmbhat/pyttsx3) - Text-to-Speech
- [Llama 3](https://llama.meta.com/) - Local language model

Happy coding! 🚀
