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
```bash
edureach/
├── server/
│   ├── knowledge-base/
│   │   └── edureach-knowledge.txt          # Knowledge base text file
│   │
│   ├── src/
│   │   ├── config/
│   │   │   └── database.config.ts          # MongoDB connection
│   │   │
│   │   ├── controllers/
│   │   │   ├── auth.controller.ts          # Register, Login, GetMe
│   │   │   ├── chat.controller.ts          # Chat message handler
│   │   │   └── vapi.controller.ts          # Vapi call handler
│   │   │
│   │   ├── middleware/
│   │   │   ├── auth.middleware.ts          # JWT verification
│   │   │   └── error-handler.middleware.ts # Error handling
│   │   │
│   │   ├── models/
│   │   │   ├── user.model.ts               # User schema
│   │   │   └── knowledge-doc.model.ts      # Knowledge document schema
│   │   │
│   │   ├── routes/
│   │   │   ├── auth.routes.ts              # Auth routes
│   │   │   ├── chat.routes.ts              # Chat routes
│   │   │   └── vapi.routes.ts              # Vapi routes
│   │   │
│   │   ├── services/
│   │   │   ├── rag.service.ts              # RAG pipeline + agent
│   │   │   └── vapi.service.ts             # Vapi API integration
│   │   │
│   │   ├── utils/
│   │   │   ├── jwt.util.ts                 # JWT sign/verify
│   │   │   └── password.util.ts            # Password hash/compare
│   │   │
│   │   ├── app.ts                          # Express app setup
│   │   └── server.ts                       # Server entry point
│   │
│   ├── .env                                # Environment variables
│   ├── package.json
│   └── tsconfig.json
│
├── client/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Navbar.tsx                  # Navigation
│   │   │   ├── HeroSection.tsx             # Hero banner
│   │   │   ├── AboutSection.tsx            # About section
│   │   │   ├── AchievementsSection.tsx     # Stats counter
│   │   │   ├── CoursesSection.tsx          # Course cards
│   │   │   ├── QuotesSection.tsx           # Testimonials
│   │   │   ├── MentorsSection.tsx          # Faculty cards
│   │   │   ├── StudentLifeSection.tsx      # Gallery
│   │   │   ├── HiringStatsSection.tsx      # Placement stats
│   │   │   ├── EventsGallery.tsx           # Events
│   │   │   ├── CounselorCTA.tsx            # Call CTA
│   │   │   ├── Footer.tsx                  # Footer
│   │   │   ├── SignupPopup.tsx             # Scroll popup
│   │   │   ├── ChatDrawer.tsx              # Chat interface
│   │   │   ├── FloatingChatButton.tsx      # Chat button
│   │   │   └── CallPopup.tsx               # Call form
│   │   │
│   │   ├── context/
│   │   │   └── AuthContext.tsx             # Auth state management
│   │   │
│   │   ├── data/
│   │   │   └── content.ts                 # Static content
│   │   │
│   │   ├── pages/
│   │   │   ├── HomePage.tsx               # Main page
│   │   │   ├── LoginPage.tsx              # Login form
│   │   │   └── SignupPage.tsx             # Signup form
│   │   │
│   │   ├── services/
│   │   │   ├── api.ts                     # Axios instance
│   │   │   ├── auth.service.ts            # Auth API calls
│   │   │   ├── chat.service.ts            # Chat API calls
│   │   │   └── vapi.service.ts            # Vapi API calls
│   │   │
│   │   ├── App.tsx                        # App root
│   │   ├── main.tsx                       # Entry point
│   │   └── index.css                      # Tailwind styles
│   │
│   ├── package.json
│   └── vite.config.ts
│
└── README.md
```

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
