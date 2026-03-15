# 🎓 Nova — AI Study Tutor

An AI-powered personal tutor that takes student notes and adapts its teaching to the student's understanding level. Built with Node.js/Express and Claude AI.

---

## ✨ Features

- **Upload notes** — supports `.txt`, `.md`, `.pdf`, `.docx` files or paste directly
- **Adaptive assessment** — Nova quizzes the student before teaching to gauge prior knowledge
- **Personalised teaching** — focuses on weak areas, uses real-world examples and analogies
- **Audio support** — text-to-speech for all AI responses + voice input (speech-to-text)
- **Gamification** — XP points, badges, progress bars, and confetti celebrations
- **Streaming responses** — real-time word-by-word AI output
- **Weakness tracking** — identifies and highlights topics that need more attention

---

## 🚀 Deploy to Render (Recommended)

### Step 1: Push to GitHub

```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/YOUR_USERNAME/ai-tutor.git
git push -u origin main
```

### Step 2: Create a Render Web Service

1. Go to [render.com](https://render.com) and sign in
2. Click **New → Web Service**
3. Connect your GitHub repository
4. Configure the service:
   - **Name:** `nova-ai-tutor` (or any name)
   - **Environment:** `Node`
   - **Build Command:** `npm install`
   - **Start Command:** `npm start`
   - **Plan:** Free (or paid for always-on)

### Step 3: Set Environment Variables

In your Render service dashboard → **Environment** tab, add:

| Key | Value |
|-----|-------|
| `ANTHROPIC_API_KEY` | `sk-ant-api03-...` (your key from console.anthropic.com) |

### Step 4: Deploy

Click **Deploy**. Render will build and start the service. Your app will be live at:
`https://nova-ai-tutor.onrender.com`

---

## 💻 Run Locally

```bash
# 1. Clone / download the project
cd ai-tutor

# 2. Install dependencies
npm install

# 3. Set up environment
cp .env.example .env
# Edit .env and add your ANTHROPIC_API_KEY

# 4. Start the server
npm start

# Visit http://localhost:3000
```

---

## 📁 Project Structure

```
ai-tutor/
├── server.js          # Express server + Claude API proxy + file parsing
├── package.json
├── .env.example
├── .gitignore
└── public/
    └── index.html     # Complete single-page app (HTML + CSS + JS)
```

---

## 🔑 Getting an Anthropic API Key

1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Sign up / log in
3. Navigate to **API Keys**
4. Create a new key and copy it
5. Add it to your `.env` file or Render environment variables

---

## 🎮 How It Works

1. **Upload** your notes (PDF, Word doc, text file, or paste)
2. Nova **assesses** your current understanding with diagnostic questions
3. Nova identifies **weak areas** and builds a personalized lesson plan
4. **Interactive teaching** with quizzes, challenges, and real-world examples
5. Earn **XP and badges** as you learn
6. Use 🔊 to listen to any response, or 🎤 to speak your answers

---

## 📦 Tech Stack

- **Backend:** Node.js + Express
- **AI:** Anthropic Claude (claude-sonnet-4)
- **File parsing:** pdf-parse, mammoth (docx)
- **Frontend:** Vanilla HTML/CSS/JS (no framework, zero build step)
- **Audio:** Web Speech API (built into browser)
- **Hosting:** Render

---

## ⚠️ Notes

- The free Render tier spins down after 15 minutes of inactivity (first request may be slow to wake)
- Upgrade to a paid Render plan for always-on availability
- File uploads are processed in memory (not stored on disk)
- Voice features require Chrome, Edge, or Safari (not Firefox for STT)
