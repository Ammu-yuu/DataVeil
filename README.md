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

Frontend: React + Tailwind CSS (TypeScript)

Backend: Node.js (Express) or Next.js API routes (TypeScript)

Database: PostgreSQL or MongoDB

OSINT Tools:

Sherlock – username enumeration across platforms
​

HaveIBeenPwned API – breach exposure checking
​

Satellite Data: N2YO REST API for satellite positions/overpasses


Functional Requirements

User Authentication & Access Control: Users can register, log in and log out securely. Passwords are hashed; sessions use HTTP‑only cookies. Only authenticated users can access OSINT and satellite modules.

OSINT Lookup Module: User submits a username or email. Backend runs Sherlock (for usernames) or calls HIBP (for emails) and returns normalised results. Results show: platform, status (found/not found), link, basic metadata.

Satellite Tracker Module: User enters coordinates or chooses a city/region. Backend calls N2YO to list satellites currently visible or passing within a given time window. Frontend displays satellites on a map with basic info (name, ID, altitude, time).

Exposure View & Reports: For a lookup, the app aggregates OSINT + satellite context and computes a simple “exposure score”. User can view a summary card and export a short text/JSON report.

Audit Logging & History: Every lookup (who, what, when, type) is stored in the DB. User can view their own history; admins can view system‑wide history.

Security & Privacy Controls: Input validation on usernames, emails, coordinates and file uploads. Rate limits on OSINT endpoints; API keys stored in environment variables.


A “Privacy & Ethics” page explaining intended use and limitations.

Threat Modelling (Short)
Assets: OSINT results, user accounts, API keys, audit logs.

Actors: legitimate user, malicious user, API abuser, external attacker.

Key Risks: account takeover, abuse of OSINT APIs, XSS, IDOR, data leakage.

Mitigations: strong auth, rate limiting, validation/encoding, access checks, logging.

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
