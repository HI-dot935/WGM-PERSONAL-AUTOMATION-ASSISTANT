---
title: WGM AI Voice Assistant
sdk: gradio
sdk_version: 4.0.0
app_file: app.py
pinned: true
license: mit
short_description: Cross-platform AI voice assistant — J.A.R.V.I.S style
---

# W·G·M — AI Voice Assistant

> *Cross-platform AI voice assistant. J.A.R.V.I.S-style personality. OpenRouter powered.*

---

## What is WGM?

WGM is a fully local, cross-platform AI voice assistant built in Python — runs on **Windows, macOS, and Linux**. Speak naturally and WGM responds with a J.A.R.V.I.S-style personality, powered by OpenRouter's free AI models with automatic fallback.

This HuggingFace Space is a **live web demo** of the conversation engine. The full local version does a lot more (see below).

---

## Full Local Features

| Feature | Voice Command Example |
|---|---|
| 🤖 AI conversation | *"explain quantum computing"* |
| 🔍 4-source web search | *"search the web for latest AI news"* |
| 📂 File search by voice | *"find my resume"*, *"find all pdf files"* |
| 🌐 Web app launcher | *"open google docs"*, *"launch figma"* |
| 🔗 200+ site launcher | *"open netflix in chrome"* |
| 📱 App launcher | *"open vscode"*, *"open spotify"* |
| 🌤️ Weather | *"weather in Mumbai"* |
| 📰 News | *"latest news on AI"* |
| 📖 Wikipedia | *"wikipedia about black holes"* |
| ⏰ Time & Date | *"what time is it"* |
| 🔊 Volume control | *"volume up"*, *"mute"* |
| 📸 Screenshot | *"take a screenshot"* |
| 🎵 Music player | *"play music"* |
| 📡 WiFi info | *"what network am i on"* |
| 😄 Jokes | *"tell me a joke"* |
| 💰 Paid model support | flip `USE_PAID_MODEL = True` |

---

## How to Run Locally

```bash
# 1. Clone
git clone https://github.com/YOUR_USERNAME/WGM-Voice-Assistant
cd WGM-Voice-Assistant

# 2. Install
pip install -r requirements.txt

# 3. Add your OpenRouter key (free at openrouter.ai)
#    Open WGM-ALL-DEVICES.py and paste key on line ~121

# 4. Run
python WGM-ALL-DEVICES.py

# Quick test (no mic needed)
python WGM-ALL-DEVICES.py "what time is it"
python WGM-ALL-DEVICES.py "give me a report on India GDP"
```

---

## AI Models Used (Free)

WGM auto-tries these in order — falls back if one is down:

1. `qwen/qwen3-8b:free` — primary
2. `meta-llama/llama-3.3-70b-instruct:free` — fallback 1
3. `google/gemma-3-27b-it:free` — fallback 2
4. `mistralai/mistral-7b-instruct:free` — fallback 3
5. `openrouter/auto` — last resort

Paid models supported too — set `USE_PAID_MODEL = True` and pick any model from [openrouter.ai/models](https://openrouter.ai/models).

---

## Requirements (Local)

```
pyautogui~=0.9.54
SpeechRecognition~=3.10.4
requests~=2.31.0
wikipedia~=1.4.0
pyjokes==0.6.0
pyttsx3~=2.90
pyaudio~=0.2.14
```

---

## Platform Support

| Platform | TTS | Volume | Screenshots | Apps |
|---|---|---|---|---|
| macOS 10.15+ | `say` command | osascript | screencapture | `open -a` |
| Windows 10/11 | pyttsx3 SAPI5 | pycaw/ctypes | pyautogui | os.startfile |
| Linux Ubuntu 20+ | pyttsx3 espeak | amixer | scrot | xdg-open |

---

*Built with Python · OpenRouter · DuckDuckGo · Wikipedia · Gradio*
