# 🚀 AI Interview Assistant Pro

AI-powered mock interview platform with real-time voice conversation, dynamic question generation, and intelligent evaluation.

## Features

- 🎤 **Voice Mode** - Full hands-free interview with TTS/STT
- 🤖 **AI-Driven Questions** - Dynamic, adaptive questioning powered by GPT-4o-mini
- 📊 **Smart Evaluation** - Scored across Technical, Problem Solving, Communication, Confidence
- 📄 **Resume Parsing** - Upload your resume for personalized questions
- 🌙 **Dark Mode** - Beautiful dark/light theme toggle
- 📱 **Mobile-First** - Responsive design optimized for all screen sizes

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React + Vite + TailwindCSS v4 + Zustand |
| Backend | Node.js + Express + WebSocket |
| AI | OpenAI GPT-4o-mini |
| Voice | ElevenLabs TTS + Whisper STT |
| Database | Supabase (PostgreSQL) |

## Quick Start

### 1. Clone & Install

```bash
# Install frontend dependencies
cd frontend
npm install

# Install backend dependencies
cd ../backend
npm install
```

### 2. Configure Environment

```bash
# Copy the example env and fill in your keys
cp .env.example backend/.env
```

Edit `backend/.env` with your API keys:
- `OPENAI_API_KEY` - Get from [OpenAI](https://platform.openai.com)
- `ELEVENLABS_API_KEY` - Get from [ElevenLabs](https://elevenlabs.io)
- `SUPABASE_URL` + `SUPABASE_ANON_KEY` - Get from [Supabase](https://supabase.com)

### 3. Setup Database

Run the SQL schema in your Supabase SQL Editor:
```
backend/src/db/schema.sql
```

### 4. Run Development Servers

```bash
# Terminal 1 - Backend
cd backend
npm run dev

# Terminal 2 - Frontend
cd frontend
npm run dev
```

Open [http://localhost:5173](http://localhost:5173)

## Project Structure

```
├── frontend/           # React + Vite app
│   ├── src/
│   │   ├── pages/      # Landing, Dashboard, Setup, Chat, Report, History
│   │   ├── store/      # Zustand stores (auth, interview, theme)
│   │   └── services/   # API client
│   └── index.html
├── backend/            # Node.js + Express API
│   └── src/
│       ├── routes/     # Auth, Interview, Voice endpoints
│       ├── services/   # AI, Supabase, Resume parser
│       ├── middleware/  # JWT auth
│       └── db/         # SQL schema
├── mobile/             # React Native (Expo) - future
├── shared/             # Shared types/constants
└── .env.example
```

## API Endpoints

| Method | Endpoint | Description |
|--------|---------|-------------|
| POST | `/api/auth/login` | Email login |
| POST | `/api/auth/signup` | Create account |
| POST | `/api/auth/google` | Google OAuth |
| POST | `/api/interview/start` | Start new session |
| POST | `/api/interview/generate-question` | Get next AI question |
| POST | `/api/interview/submit-answer` | Submit answer |
| POST | `/api/interview/evaluate` | Get final evaluation |
| GET | `/api/interview/history` | Interview history |
| POST | `/api/voice/tts` | Text-to-Speech |
| POST | `/api/voice/stt` | Speech-to-Text |

## Deployment

- **Frontend**: Deploy `frontend/` to Vercel or Netlify
- **Backend**: Deploy `backend/` to Render or Railway
- **Database**: Supabase (already cloud-hosted)

## License

MIT
