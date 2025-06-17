# 🤖 AI Customer Support System – Proof of Concepts (PoC-1 & PoC-2)

This repository contains two Proof-of-Concept (PoC) systems developed to automate customer support using AI. One handles **voice-based calls** (PoC-1), while the other manages **chat-based support** (PoC-2). Developed as part of the **Cogniwide Python Developer Assignment**.

---

## 🧠 PoC-1: AI Voice Agent System

A FastAPI-based voice assistant that handles **inbound and outbound voice calls** using speech-to-text (STT), text-to-speech (TTS), intent detection, and conversation logging.

### 🚀 Features

- 📞 Outbound calling using AI voice (via Vapi/Twilio).
- ☎️ Inbound call reception and voice processing.
- 🗣️ Speech-to-text using Deepgram or OpenAI Whisper.
- 🧠 Intent detection with OpenAI or rule-based logic.
- 🔊 TTS generation using ElevenLabs or mock TTS.
- 🗂️ Conversation and ticket logging in SQLite.
- 🌐 Simple HTML frontend for demonstration.

### 🗂️ Project Structure

```
poc1_voice_assistant/
├── main.py              # FastAPI entry point
├── call_logic.py        # Call handling logic
├── stt.py               # Speech-to-text utility
├── tts.py               # Text-to-speech logic
├── intent.py            # Intent classification
├── database.py          # SQLite DB interactions
├── utils.py             # Logging helpers
├── static/              # HTML/CSS frontend
├── output/              # Generated audio files
└── .env                 # API keys (excluded from repo)
```

### ▶️ How to Run

```bash
# Clone the repository
git clone https://github.com/yourusername/your-repo-name.git
cd your-repo-name/poc1_voice_assistant

# Create a virtual environment (optional)
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows

# Install dependencies
pip install -r requirements.txt

# Start the FastAPI server
uvicorn main:app --reload
```

- API: `http://localhost:8000/docs`
- Frontend: `http://localhost:8000/static/index.html`

---

## 💬 PoC-2: AI Multi-Agent Chat Support System

A modular FastAPI system where AI agents collaborate to handle chat-based customer queries, classify intents, and automate responses or ticket creation.

### 🚀 Features

- 🔍 `IntentClassifierAgent` — Classifies query type.
- 🧭 `RoutingAgent` — Routes to the correct support agent.
- 🤖 `SupportAgents`:
  - `FAQAgent`: Returns predefined answers.
  - `TicketAgent`: Logs issues.
  - `AccountAgent`: Handles account-related logic.
- 🔔 `NotifyAgent`: Sends updates via email or WhatsApp.
- 🧠 Intent logic powered by OpenAI or keyword rules.
- 🗂️ SQLite DB for chat logs and tickets.
- ⚡ Async processing and robust logging.
- 🌐 Built-in Swagger UI for testing.

### 🗂️ Project Structure

```
poc2_multi_agent_chat/
├── main.py               # FastAPI entry point
├── agents/
│   ├── intent_classifier.py
│   ├── router.py
│   ├── faq_agent.py
│   ├── ticket_agent.py
│   ├── account_agent.py
│   └── notify_agent.py
├── db/
│   └── models.py         # SQLite database models
├── utils/
│   └── logger.py         # Logging utility
└── .env                  # Environment variables
```

### ▶️ How to Run

```bash
# Navigate to project folder
cd poc2_multi_agent_chat

# (Optional) Create virtual environment
python -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Start the FastAPI server
uvicorn main:app --reload
```

- Swagger UI: `http://127.0.0.1:8000/docs`

---

## 🔐 Environment Setup

Create a `.env` file at the project root and configure with the following:

```
OPENAI_API_KEY=your_openai_key
DEEPGRAM_API_KEY=your_deepgram_key
ELEVENLABS_API_KEY=your_elevenlabs_key
TWILIO_ACCOUNT_SID=your_twilio_sid
TWILIO_AUTH_TOKEN=your_twilio_token
EMAIL_API_KEY=your_sendgrid_key_or_mock
```

> ⚠️ **Note**: Do not commit `.env` to version control.

---

## 🧰 Tech Stack

| Feature          | Tech Used                            |
|------------------|---------------------------------------|
| Backend          | Python + FastAPI                      |
| STT/TTS          | Deepgram, Whisper, ElevenLabs         |
| AI/NLP           | OpenAI GPT                            |
| Voice Calls      | Vapi or Twilio                        |
| Notifications    | Twilio SMS / SendGrid Email           |
| Database         | SQLite                                |
| Frontend         | Basic HTML/CSS                        |

---

## 💡 Bonus Features

- ✅ Multi-language support (e.g., Hindi, Tamil)
- ✅ Minimal frontend for demo interaction
- ✅ Modular agent design for easy extension
- ✅ Error handling and logging

---

## 🐳 Optional: Docker Setup

```bash
# Build and run the container
docker build -t ai-support-poc .
docker run -p 8000:8000 ai-support-poc
```

---

## 📌 Future Improvements

- ✅ Cloud deployment (Render, Railway, Heroku)
- ✅ Enhanced frontend for playback & chat interface
- ✅ Live agent handoff simulation
- ✅ Production-grade monitoring/logs

---

## 👤 Author

**Shivam**  
Python Developer  
[GitHub](https://github.com/Shivu384) • [LinkedIn](https://linkedin.com/in/shivamarora384)

---

## 📄 License

This project is licensed under the MIT License.
