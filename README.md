🛰️ DataVeil

OSINT & Exposure-Awareness Dashboard

DataVeil is a web-based security analysis dashboard that demonstrates how publicly available information (OSINT) can be correlated and visualised to understand digital exposure, activity context, and potential risk signals.

The project is designed as a defensive, educational tool for security analysts, students, and engineers to explore how fragmented public data can be combined — and why monitoring, logging, and ethical handling of data are critical in modern security operations.

🎯 Project Goals

Demonstrate defensive OSINT analysis using publicly available data

Visualise contextual relationships (identity, geography, time-based activity)

Highlight how data exposure can emerge from benign sources

Practice secure backend design, logging, and API integration

Build a full-stack system with security-first thinking

This project is not intended for surveillance, tracking individuals, or invasive investigation.

🔍 Core Features
🛰️ Satellite Visibility Tracker

Fetches real-time satellite position and visibility data using the N2YO API

Displays satellites over a selected geographic region

Provides context for understanding satellite coverage and activity

🕵️ OSINT Username Scan

Uses Sherlock to identify publicly available usernames across platforms

Returns only information that is already public and openly accessible

No authenticated, private, or restricted content is accessed

🗺️ Geospatial Visualisation

Interactive map view using Leaflet

Overlays satellite paths and regional visibility

Helps correlate location-based context with public activity

📝 Snapshot Logging & Audit Trail

Stores user-initiated searches and results

Creates a basic audit trail to demonstrate:

Traceability

Accountability

Investigation context

🔐 Security Controls

Rate limiting on backend APIs

Input validation

Controlled execution of external tools

Environment-based API key management

🧱 Tech Stack
Frontend

React

TypeScript

Tailwind CSS

Leaflet.js (maps)

Backend

Node.js (Express) or Next.js API routes

REST APIs

Python (for controlled OSINT tooling execution)

Database

PostgreSQL (or MongoDB)

Stores search logs, snapshots, and metadata

External APIs & Tools

N2YO API – satellite data

Sherlock – username OSINT (public platforms only)

Hosting (Planned)

Frontend: Vercel

Backend & DB: Railway / Render

📐 System Architecture (High-Level)
Frontend (React)
   ↓ REST API
Backend (Node.js / Express)
   ├── Satellite API Integration (N2YO)
   ├── OSINT Tool Runner (Python - Sherlock)
   ├── Rate Limiting & Logging
   ↓
Database (PostgreSQL)

🧠 Ethical & Legal Considerations

DataVeil is built with ethics and legality as a core principle:

✅ Only publicly available data is accessed

❌ No scraping of private or authenticated content

❌ No tracking of individuals without user-initiated input

❌ No automated profiling or decision-making

This project exists to:

Educate on data exposure risks

Encourage responsible security thinking

Demonstrate defensive analysis techniques

Important: This tool should only be used for educational, research, or defensive security purposes.

🧪 Testing (Planned / In Progress)

Unit tests for satellite API integrations

Mocked OSINT tool output for backend testing

Input validation tests

UI tests for search workflows

🚀 Getting Started
Prerequisites

Node.js (v18+)

Python 3.x

PostgreSQL or MongoDB

N2YO API Key

Setup
git clone https://github.com/your-username/dataveil
cd dataveil

# Backend
cd backend
npm install
npm run dev

# Frontend
cd frontend
npm install
npm run dev


Create a .env file with:

N2YO_API_KEY=your_key_here
DATABASE_URL=your_db_url

🛣️ Roadmap

 Improve audit trail visualisation

 Add investigation notes per snapshot

 Enhance rate limiting & abuse detection

 Exportable exposure summary reports

 Alerting for defined conditions (educational use)

📚 What This Project Demonstrates

Full-stack development with security awareness

API integration and data orchestration

Ethical OSINT usage

Logging, auditing, and traceability

Clear documentation and system thinking
