# 🌾 Farmer Scheme AI Assistant (VJTI M-Indicator Hackathon)

An AI-powered ecosystem designed to bridge the digital divide for Indian farmers by providing seamless, multilingual access to government schemes via a **Modern Web Dashboard**, **Multilingual IVR (Phone Calls)**, and **WhatsApp Chatbots**.

## 🚀 Key Features

*   **🌐 Kisan Yojana Sahayak (Web Dashboard)**: A premium, mobile-first web application supporting **7 Indian languages**. Features a farm-themed UI designed for maximum accessibility and a built-in AI chat interface.
*   **📞 Multilingual Voice AI (IVR)**: A phone-based assistant supporting **Hindi, Marathi, and English**. Farmers can get scheme recommendations and check eligibility simply by talking on a standard phone call.
*   **💬 Multilingual WhatsApp Bot**: A robust chatbot supporting **5+ Indian languages**. Features include location-based weather analysis and seamless conversational flows.
*   **👁️ AI Document Verification**: Uses **Llama 4 Scout (VLM)** to automatically verify uploaded documents like Aadhaar cards, PAN cards, or Land Records in real-time.
*   **🌦️ Climate-Smart Recommendations**: Analyzes 30-day historical weather data to suggest relevant insurance schemes like PMFBY if the farmer's region faced unseasonal rain or drought.
*   **📝 Automated Form Filling**: Converts complex government application forms (KCC, PM-KISAN, PMFBY, NLM) into simple, step-by-step chat conversations.
*   **⚡ Reverse RAG (Proactive Alerts)**: A proactive system that scans farmer profiles in the vector database and sends outbound WhatsApp alerts when a new matching scheme is announced.

## 🛠️ Tech Stack

### Frontend
- **Framework**: [Next.js 15+](https://nextjs.org/) (React 19)
- **Styling**: [Tailwind CSS 4](https://tailwindcss.com/)
- **Animations**: [Framer Motion](https://www.framer.com/motion/)
- **Icons**: [Lucide React](https://lucide.dev/)

### Backend
- **Framework**: [FastAPI](https://fastapi.tiangolo.com/) (Python)
- **LLM**: **GPT OSS** (Core Intelligence)
- **VLM**: **Llama 4 Scout** (Vision Verification)
- **STT**: **Groq Whisper-large-v3**
- **TTS**: **ElevenLabs** (Multilingual v2)

### Infrastructure
- **Vector DB**: **ChromaDB**
- **Communication**: **Twilio** (Voice & WhatsApp)
- **Weather**: **Open-Meteo API**

## 📁 Project Structure

```text
.
├── frontend/               # Next.js Multilingual Dashboard
│   ├── app/                # App router logic & styles
│   ├── components/         # Animated UI components
│   └── lib/                # Translation libraries (7 languages)
├── main.py                 # FastAPI Application Gateway
├── ivr.py                  # Twilio IVR voice flow logic
├── whatsapp_webhook.py     # WhatsApp webhook management
├── auto_form_filling.py    # Conversational form logic
├── weather_schemes.py      # Weather analysis & recommendations
├── data_input.py           # Core LLM-driven chatbot logic
├── scripts/
│   ├── rag.py              # Retrieval Augmented Generation
│   └── chroma_db/          # Persistent Vector Storage
└── static/                 # Static assets & generated audio
```

## ⚙️ Environment Variables

Create a `.env` file in the root directory and add the following:

```env
# API Keys
GROQ_API_KEY=your_groq_api_key
ELEVENLABS_API_KEY=your_elevenlabs_api_key

# Twilio Configuration
TWILIO_ACCOUNT_SID=your_sid
TWILIO_AUTH_TOKEN=your_token
TWILIO_PHONE_NUMBER=your_twilio_number
TWILIO_WHATSAPP_NUMBER=your_whatsapp_sandbox_number

# Webhook URLs
NGROK_URL=https://your-ngrok-url.ngrok-free.app
```

## 🛠️ Installation & Setup

### 1. Clone the repository
```bash
git clone <repository-url>
cd VJTI-M-Indicator-Hackathon
```

### 2. Backend Setup (FastAPI)
1. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
2. **Run the server**:
   ```bash
   uvicorn main:app --reload
   ```

### 3. Frontend Setup (Next.js)
1. **Navigate to the frontend directory**:
   ```bash
   cd frontend
   ```
2. **Install dependencies**:
   ```bash
   pnpm install
   ```
3. **Run the development server**:
   ```bash
   npm run dev
   ```

### 4. Expose to Web (for Webhooks)
```bash
ngrok http 8000
```
Update the `NGROK_URL` in your `.env` with the provided ngrok link.

---
*Built for the VJTI M-Indicator Hackathon.*