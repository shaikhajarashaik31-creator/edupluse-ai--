# 🚀 EduPulse AI — Autonomous Student Analytics & Success Platform

> **"Track the pulse of every student's success."**  
> A production-grade, full-stack educational intelligence platform built with React 18, Vite, Tailwind CSS, Node.js, Express, SQLite, and Google Gemini AI.

---

## 🌟 Highlights & Features

### 🎓 1. Student Hub & Academic Success
- **Executive Dashboard:** Live 15s telemetry polling via `usePolling.js`. Displays weighted performance %, attendance rate %, coin treasury balance, enrolled courses, and performance evolution charts.
- **Dynamic 40/25/20/15 Weighted Performance:** Automatically computes student standing:
  - **40%** Mock Tests
  - **25%** Coding Practice Arena
  - **20%** Course Lesson Completion
  - **15%** Class Attendance
  Tracks historical trajectory in `performance_history` table.
- **Authentic Handwritten Notebook:**
  - Styled with lined paper lines, vertical red margin, realistic spiral binding, and Google Font **Caveat**.
  - Synthesizes **5 distinct structured pages** per lecture with embedded SVG conceptual diagrams.
  - Table of Contents sidebar, search & filter, "Mark as Revised" toggle, print-to-PDF, and "Request Past Notes" generator modal.
- **20+ Courses Across 12 Categories & Course Store:**
  - Standard curriculum & paid electives across Web Dev, AI, Data Science, DevOps, Cybersecurity, Mobile, and more.
  - Category filters, coin affordability checks, and atomic SQLite transaction paid enrollment.
- **Sequential Lesson Player & Certification:**
  - Step-by-step reading modules (+5 Coins awarded per completion).
  - Comprehensive Final Certification Quiz (70% passing threshold).
  - Passing issues an official verifiable certificate and awards **+100 Bonus Coins**!
- **Verifiable Digital Credentials & QR Code:**
  - Unique credential code (`CERT-XXXXXX`).
  - Scannable QR code directing to public verification `/verify/:code`.
- **40-Problem Coding Practice Arena:**
  - Categorized by topic (Arrays, Strings, Dynamic Programming, Graphs, Trees, etc.) and difficulty (Easy, Medium, Hard).
  - In-browser Monaco editor with multi-language selector.
  - "Run Sample Testcases" vs "Submit Hidden Testcases".
  - First-solve coin awards (Easy: +10, Medium: +25, Hard: +50) with idempotency guards and confetti.
  - Topic Mastery bar chart and streak tracking.
- **AI Resume Builder & ATS Scorer:**
  - Target Role selector (Full Stack Engineer, Web Dev, Data Analyst, ML Engineer, DevOps, Java Dev, Cyber Security).
  - Recharts bar chart showing ATS category breakdown (Action Verbs, Metrics, Role Keywords, Formatting).
  - Missing keywords chips.
  - "Improve with AI" button that rewrites bullet points to include action verbs, metrics, and target skills.
  - Dual live templates: **Modern Tech** and **Classic Academic**.
- **EduPulse Coin Treasury & History:**
  - Real-time balance card, lifetime earned & spent stats.
  - Filterable transaction ledger with reference keys.
  - Earning guide with direct navigation links.
- **ChatGPT-Style AI Mentor:**
  - Multi-session drawer (New Chat, inline Rename, Delete).
  - Real-time Server-Sent Events (SSE) streaming responses with typewriter effect.
  - Markdown rendering with dark syntax-highlighted code blocks and **Copy Code** button.
  - **Stop Generating** button to abort in-flight requests.
  - Contextual memory sending conversation history and personalized student profile to Gemini.

---

### 👨‍🏫 2. Faculty Portal
- **Faculty Dashboard:** Live 15s polling tracking student engagement, course distribution, and attendance.
- **Student Roster & Risk Triage:** Filter between all students, at-risk (<80% attendance or <75% performance), and honors students.
- **Attendance Marking:** Mark attendance per student with automated lecture notes generation trigger for absent records.
- **Strict 80/80 High-Achiever Feedback Synthesis:**
  - Evaluates student feedback strictly from students with **Attendance ≥ 80% AND Course Score ≥ 80%**.
  - **Cohort Threshold Alert:** If fewer than 3 students qualify, displays a clear warning card showing qualifying students and explains why cohort-wide synthesis is withheld.
  - Generates **5 structured pedagogical action points** for teachers when threshold is met.

---

### 🏛️ 3. Administrative Console & Token Economy
- **Platform Governance Dashboard:** Real-time metrics on students, teachers, courses, today's logins, and department breakdowns.
- **User Provisioning & Password Security:**
  - Create faculty or student accounts with auto-generated secure temporary passwords (shown once with 1-click copy).
  - Reset any user's password to an auto-generated temporary credential.
  - Enforces `must_change_password = 1` redirecting users to the secure `/change-password` checklist on login.
- **Platform Token Economy Dashboard:**
  - Total Coins Minted vs Total Coins Spent on Electives.
  - Net Circulation and Active Wallet Holders count.
  - Largest Student Treasuries Leaderboard and live global ledger feed.

---

## 🔐 Individual Passwords & Demo Credentials

Every user has their **own individual unique password** stored as a salted bcrypt hash.  
All seeded credentials have been generated and documented in:
👉 [`backend/db/demo_credentials.txt`](file:///backend/db/demo_credentials.txt)

### Quick Credential Reference:

| Role | Email | Name | Default Seed Password |
|---|---|---|---|
| **Admin** | `admin@admin.edu` | Dr. Arthur Pendelton | `Arthur#Admin9` |
| **Teacher** | `sarah.jenkins@teacher.edu` | Prof. Sarah Jenkins | `Sarah#Teach8` |
| **Teacher** | `david.kumar@teacher.edu` | Dr. David Kumar | `David#Teach4` |
| **Student** | `alex.chen@student.edu` | Alex Chen | `Alex@CS101` |
| **Student** | `rahul.sharma@student.edu` | Rahul Sharma | `Rahul@CS102` |
| **Student** | `ava.thomas@student.edu` | Ava Thomas | `Ava@CS103` |
| **Student** | `priya.patel@student.edu` | Priya Patel | `Priya@DS201` |
| **Student** | `sophia.martinez@student.edu` | Sophia Martinez | `Sophia@CS104` |
| **Student** | `marcus.vance@student.edu` | Marcus Vance | `Marcus@CS105` |
| **Student** | `chloe.bennett@student.edu` | Chloe Bennett | `Chloe@CS106` |
| **Student** | `ethan.hunt@student.edu` | Ethan Hunt | `Ethan@DS202` |
| **Student** | `zara.ali@student.edu` | Zara Ali | `Zara@CS107` |
| **Student** | `liam.nguyen@student.edu` | Liam Nguyen | `Liam@DS203` |
| **Student** | `maya.lin@student.edu` | Maya Lin | `Maya@CS108` |
| **Student** | `noah.clark@student.edu` | Noah Clark | `Noah@CS109` |

> 💡 **Password Security Rule:** Seeded users have `must_change_password = 1`. Upon initial login, you will be prompted to set a personal password (min 8 characters, at least 1 number, at least 1 symbol).  
> 💡 **1-Click Login:** The login page also features convenient 1-click test buttons that automatically populate the exact credentials!

---

## 🛠️ Technology Stack

- **Frontend:** React 18, Vite, Tailwind CSS, React Router v6, Axios, Recharts, Lucide React icons, Canvas Confetti
- **Code Editor:** `@monaco-editor/react`
- **Backend:** Node.js, Express (REST API), JWT Auth, `bcryptjs`, CORS, Dotenv
- **Database:** SQLite via `better-sqlite3` (file: `backend/db/edupulse.db`) with schema, migrations, and seeds
- **AI Engine:** Google Gemini API (`gemini-1.5-flash`) via `backend/services/aiService.js` with offline resilient mock fallbacks so the application **never crashes** if `GEMINI_API_KEY` is omitted
- **Code Execution:** Judge0 CE API via `backend/services/judge0Service.js` with sandbox fallback runner

---

## ⚡ Quick Start & Running Locally

### Option 1: Root Commands (Recommended)
From the project root:
```bash
# 1. Install root, backend, and frontend dependencies
npm run install:all

# 2. Run migrations and seed database with 23 courses, 40 coding problems, and notes
npm run seed

# 3. Start backend (Port 5000) and frontend (Port 5173) concurrently
npm run dev
```

### Option 2: Running in Separate Terminals

#### Terminal 1 (Backend on Port 5000):
```bash
cd backend
npm install
npm run seed
npm run dev
```

#### Terminal 2 (Frontend on Port 5173):
```bash
cd frontend
npm install
npm run dev
```

---

## 📡 Key API Routes

### 🔐 Auth & Identity
- `POST /api/auth/login` (Rate limited: 5 attempts / 15 minutes)
- `POST /api/auth/change-password`
- `GET /api/auth/me`

### 💻 Practice Arena & Code Execution
- `GET /api/practice/problems`
- `GET /api/practice/problems/:id`
- `POST /api/practice/run` (Sample testcase evaluation)
- `POST /api/practice/submit` (Hidden testcases evaluation + coin rewards)
- `GET /api/practice/stats`
- `POST /api/practice/hint`
- `POST /api/practice/explain`

### 📚 Courses, Lessons & Certifications
- `GET /api/courses` (Curriculum list)
- `GET /api/courses/categories` (12 categories)
- `POST /api/courses/:id/enroll` (Atomic SQLite transaction)
- `GET /api/courses/:id/lessons` (Sequential curriculum)
- `POST /api/courses/:id/lessons/:lessonId/complete` (+5 coins)
- `POST /api/courses/:id/quiz` (>= 70% issues certificate + 100 coins)
- `GET /api/verify/:code` (Public verification)

### 🤖 AI Mentor & Resume Builder
- `POST /api/ai/chat/stream` (SSE live stream)
- `GET /api/ai/sessions` (User conversation history)
- `POST /api/ai/sessions` (New conversation)
- `PATCH /api/ai/sessions/:id` (Rename conversation)
- `DELETE /api/ai/sessions/:id` (Delete conversation)
- `POST /api/ai/resume` (Generate resume)
- `POST /api/ai/resume/improve` (Improve bullets with action verbs & keywords)
- `POST /api/ai/ats-score` (Rule-based scoring)

### 🪙 Economy & Student Success
- `GET /api/student/dashboard`
- `GET /api/student/trend` (Performance evolution history)
- `GET /api/student/coins` (Treasury ledger)
- `GET /api/student/notes` (Handwritten notebook)
- `POST /api/student/notes/request` (Synthesize 5 pages of handwritten notes)
- `GET /api/admin/economy` (Platform coin circulation & metrics)
