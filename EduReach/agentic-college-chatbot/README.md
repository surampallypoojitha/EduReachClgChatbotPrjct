# 🎓 EduReach — Agentic AI College Chatbot Platform

EduReach is a **full-stack AI-powered college platform** that helps students instantly access accurate information about courses, fees, admissions, placements, and campus life.

It combines a **modern web application**, an **Agentic RAG chatbot**, and an **AI voice counselor** into a single intelligent system.

---

# 🌟 Key Features

## 🤖 Agentic RAG Chatbot

* Uses **Retrieval-Augmented Generation (RAG)**
* Automatically searches a **college knowledge base**
* Provides **accurate, contextual answers**
* Built using **LangChain + Google Gemini**

## 📞 AI Voice Counselor

* Users can request a call
* AI agent (Ava) calls and interacts in real-time
* Powered via **Vapi API**

## 🔐 JWT Authentication

* Secure login & signup
* Protects premium features (chat, voice)
* Stateless authentication system

## 🎨 Modern College Website

* Courses, mentors, placements, campus life
* Gated content for logged-in users
* Interactive UI with Tailwind CSS

---

# 🧠 System Architecture

Frontend (React + TS)
↓
Axios API Calls
↓
Backend (Node + Express)
↓
MongoDB (Users + Vector DB)
↓
LangChain + Gemini (AI Layer)

---

# 🔄 End-to-End Flow

### 🔐 Authentication Flow

User → Signup/Login → JWT generated → Stored in frontend
→ Sent in every request → Verified via middleware

---

### 🤖 Chat Flow (RAG)

User Question
→ Embedding (vector)
→ MongoDB Vector Search
→ Retrieve top 3 relevant chunks
→ Gemini generates response
→ Response sent to UI

---

### 📞 Voice Flow

User enters phone number
→ Backend calls Vapi API
→ AI agent initiates phone call

---

# 🧰 Tech Stack

## Frontend

* React + TypeScript
* Vite
* Tailwind CSS
* Axios
* React Router

## Backend

* Node.js + Express
* TypeScript
* MongoDB + Mongoose

## AI Stack

* LangChain
* Google Gemini API
* MongoDB Atlas Vector Search

## Other

* JWT (Authentication)
* bcryptjs (Password hashing)
* Vapi (Voice AI)

---

# 📁 Project Structure

```
├── server/ │ ├── knowledge-base/ │ │ └── edureach-knowledge.txt ← Knowledge base text file │ ├── src/ │ │ ├── config/ │ │ │ └── database.config.ts ← MongoDB connection (Part 1) │ │ ├── controllers/ │ │ │ ├── auth.controller.ts ← Register, Login, GetMe (Part 1) │ │ │ ├── chat.controller.ts ← Chat message handler (NEW) │ │ │ └── vapi.controller.ts ← Vapi call handler (NEW) │ │ ├── middleware/ │ │ │ ├── auth.middleware.ts ← JWT verification (Part 1) │ │ │ └── error-handler.middleware.ts ← Error handling (Part 1) │ │ ├── models/ │ │ │ ├── user.model.ts ← User schema (Part 1) │ │ │ └── knowledge-doc.model.ts ← Knowledge doc schema (NEW) │ │ ├── routes/ │ │ │ ├── auth.routes.ts ← Auth routes (Part 1) │ │ │ ├── chat.routes.ts ← Chat routes (NEW) │ │ │ └── vapi.routes.ts ← Vapi routes (NEW) │ │ ├── services/ │ │ │ ├── rag.service.ts ← RAG pipeline + agent (NEW) │ │ │ └── vapi.service.ts ← Vapi API integration (NEW) │ │ ├── utils/ │ │ │ ├── jwt.util.ts ← JWT sign/verify (Part 1) │ │ │ └── password.util.ts ← Hash/compare (Part 1) │ │ ├── app.ts ← Express app (UPDATED) │ │ └── server.ts ← Server entry (UPDATED) │ ├── .env ← Environment variables (UPDATED) │ ├── package.json │ └── tsconfig.json │ ├── client/ │ ├── src/ │ │ ├── components/ │ │ │ ├── Navbar.tsx ← Navigation (Part 1) │ │ │ ├── HeroSection.tsx ← Hero banner (Part 1) │ │ │ ├── AboutSection.tsx ← About section (Part 1) │ │ │ ├── AchievementsSection.tsx ← Stats counter (Part 1) │ │ │ ├── CoursesSection.tsx ← Course cards (Part 1) │ │ │ ├── QuotesSection.tsx ← Testimonials (Part 1) │ │ │ ├── MentorsSection.tsx ← Faculty cards (Part 1) │ │ │ ├── StudentLifeSection.tsx ← Gallery (Part 1) │ │ │ ├── HiringStatsSection.tsx ← Placement stats (Part 1) │ │ │ ├── EventsGallery.tsx ← Events (Part 1) │ │ │ ├── CounselorCTA.tsx ← Call CTA (Part 1) │ │ │ ├── Footer.tsx ← Footer (Part 1) │ │ │ ├── SignupPopup.tsx ← Scroll popup (Part 1) │ │ │ ├── ChatDrawer.tsx ← Chat interface (NEW) │ │ │ ├── FloatingChatButton.tsx ← Chat button (NEW) │ │ │ └── CallPopup.tsx ← Call form (NEW — replaces placeholder) │ │ ├── context/ │ │ │ └── AuthContext.tsx ← Auth state (Part 1) │ │ ├── data/ │ │ │ └── content.ts ← Static content (UPDATED) │ │ ├── pages/ │ │ │ ├── HomePage.tsx ← Main page (Part 1) │ │ │ ├── LoginPage.tsx ← Login form (Part 1) │ │ │ └── SignupPage.tsx ← Signup form (Part 1) │ │ ├── services/ │ │ │ ├── api.ts ← Axios instance (Part 1) │ │ │ ├── auth.service.ts ← Auth API calls (Part 1) │ │ │ ├── chat.service.ts ← Chat API calls (NEW) │ │ │ └── vapi.service.ts ← Vapi API calls (NEW) │ │ ├── App.tsx ← App root (UPDATED) │ │ ├── main.tsx ← Entry point (Part 1) │ │ └── index.css ← Tailwind styles (Part 1) │ ├── package.json │ └── vite.config.ts │ └── README.md
---

# ⚙️ Backend Overview

## 🔹 Authentication

* Register / Login / GetMe APIs
* Password hashing (bcrypt)
* JWT-based authentication

## 🔹 AI System (Core)

* Knowledge base ingestion
* Vector embeddings
* MongoDB vector search
* Agentic RAG pipeline

## 🔹 Voice Integration

* Vapi API for AI calls

---

# 🎨 Frontend Overview

## 🔹 Features

* Responsive UI
* Auth-based gated content
* Chat interface (drawer)
* Floating chat button
* Voice call popup

## 🔹 Architecture

* Context API for auth state
* Axios interceptors for JWT
* Modular component structure

---

# 🧠 Core Concepts Used

* Retrieval-Augmented Generation (RAG)
* Vector Embeddings
* JWT Authentication
* Middleware Architecture
* REST APIs
* Agent-based AI systems

---

# 🚀 Setup & Installation

## 🔹 Prerequisites

* Node.js v24+
* MongoDB Atlas account
* Google Gemini API key
* Vapi API credentials

---

## 🔹 Clone Repository

```bash
git clone https://github.com/nxtwaveacademy/EduReachCollegeChatBot.git
cd EduReachCollegeChatBot
```

---

## 🔹 Backend Setup

```bash
cd server
npm install
```

### Create `.env`

```
PORT=5000
MONGODB_URI=your_mongodb_uri
JWT_SECRET=your_secret
JWT_EXPIRES_IN=7d
CLIENT_URL=http://localhost:5173
GOOGLE_API_KEY=your_gemini_key
VAPI_API_KEY=your_vapi_key
```

---

## 🔹 Run Backend

```bash
npm run dev
```

Expected Output:

```
MongoDB Connected
EduReach Server running on port 5000
```

---

## 🔹 Frontend Setup

```bash
cd client
npm install
```

---

## 🔹 Run Frontend

```bash
npm run dev
```

Open:

```
http://localhost:5173
```

---

# ✅ How to Test the Application

## 🔐 Auth Testing

* Signup → should create user
* Login → should return token
* Refresh → user persists (via getMe)

---

## 🤖 Chat Testing

* Login required
* Open chat → ask:

  * "What is B.Tech fee?"
* Should return accurate answer from knowledge base

---

## 📞 Voice Testing

* Click "Talk to Counselor"
* Enter phone number
* AI call should be triggered

---

# 📊 Example API Testing (Postman)

### Register

```
POST /api/auth/register
```

### Login

```
POST /api/auth/login
```

### Chat

```
POST /api/chat/message
```

---

# ⚡ Strengths

* Real-world AI application
* Full-stack implementation
* Agentic RAG (advanced concept)
* Clean architecture

---

# ⚠️ Limitations

* No caching (Redis)
* No rate limiting
* No streaming responses

---

# 🔧 Future Improvements

* Redis caching for responses
* Multi-language support
* Admin dashboard
* Analytics tracking
* Deployment (Docker + CI/CD)

---

# 👩‍💻 Author

Developed as a major project for learning **AI-powered full-stack systems**.

---
