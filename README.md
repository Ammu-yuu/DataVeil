# 🛰️ DataVeil

### OSINT & Exposure-Awareness Dashboard

**DataVeil** is a web-based security analysis dashboard that demonstrates how *publicly available information (OSINT)* can be responsibly correlated and visualised to understand **digital exposure, contextual activity, and potential risk signals**.

The project is designed as a **defensive, educational tool** for security analysts, students, and engineers to explore how fragmented public data can be combined — and why **logging, monitoring, and ethical data handling** are critical in modern security operations.

> ⚠️ **Important**
> DataVeil is **not** intended for surveillance, tracking individuals, or invasive investigation.
> It focuses on awareness, defence, and ethical security analysis.

---

## 🎯 Project Goals

* Demonstrate **defensive OSINT analysis** using only publicly available data
* Visualise **contextual relationships** between identity, geography, and time-based activity
* Highlight how **data exposure can emerge from benign sources**
* Practice **secure backend design**, logging, and API integration
* Build a **full-stack system with security-first thinking**

---

## 🔍 Core Features

### 🛰️ Satellite Visibility Tracker

* Fetches real-time satellite position and visibility data using the **N2YO API**
* Displays satellites over a selected geographic region
* Provides contextual insight into satellite coverage and activity patterns

---

### 🕵️ OSINT Username Scan

* Uses **Sherlock** to identify publicly available usernames across platforms
* Returns *only* information that is already public and openly accessible
* No authenticated, private, or restricted content is accessed

---

### 🗺️ Geospatial Visualisation

* Interactive map view powered by **Leaflet**
* Overlays satellite paths and regional visibility
* Correlates location-based context with publicly observable activity

---

### 📝 Snapshot Logging & Audit Trail

* Stores user-initiated searches and results
* Creates a basic audit trail demonstrating:

  * Traceability
  * Accountability
  * Investigation context

---

### 🔐 Security Controls

* Backend API rate limiting
* Input validation and sanitisation
* Controlled execution of external OSINT tools
* Environment-based API key management

---

## 🧱 Tech Stack

**Frontend**

* React
* Tailwind CSS
* TypeScript

**Backend**

* Node.js (Express) or Next.js API routes
* TypeScript

**Database**

* PostgreSQL or MongoDB

**OSINT & External Services**

* **Sherlock** – Username enumeration across platforms
* **Have I Been Pwned API** – Breach exposure checking
* **N2YO REST API** – Satellite position and overpass data

---

## ⚙️ Functional Requirements

### 🔑 Authentication & Access Control

* Secure user registration and login
* Password hashing and HTTP-only session cookies
* Only authenticated users can access OSINT and satellite modules

---

### 🔎 OSINT Lookup Module

* User submits a username or email address
* Backend:

  * Runs **Sherlock** for usernames
  * Calls **HIBP API** for email breach checks
* Results are normalised and include:

  * Platform name
  * Status (found / not found)
  * Public link
  * Basic metadata

---

### 🛰️ Satellite Tracker Module

* User selects a city or provides latitude/longitude
* Backend calls **N2YO** to retrieve:

  * Visible satellites
  * Passing satellites within a time window
* Frontend displays results on an interactive map with:

  * Satellite name
  * ID
  * Altitude
  * Timestamp

---

### 📊 Exposure View & Reports

* Aggregates OSINT results with geospatial context
* Computes a simple **exposure score**
* Displays a summary card per lookup
* Allows export of results as text or JSON reports

---

### 🧾 Audit Logging & History

* Stores every lookup:

  * Who performed it
  * What was searched
  * When it occurred
  * Lookup type
* Users can view their own history
* Admins can view system-wide activity

---

### 🔐 Security & Privacy Controls

* Input validation for usernames, emails, coordinates
* Rate limiting on OSINT-related endpoints
* API keys stored securely in environment variables
* Dedicated **Privacy & Ethics** page outlining:

  * Intended use
  * Limitations
  * Legal considerations

---

## 🛡️ Threat Modelling (Summary)

**Assets**

* OSINT results
* User accounts
* API keys
* Audit logs

**Threat Actors**

* Legitimate users
* Malicious users
* API abusers
* External attackers

**Key Risks**

* Account takeover
* OSINT API abuse
* XSS / injection attacks
* IDOR
* Data leakage

**Mitigations**

* Strong authentication
* Rate limiting
* Input validation and output encoding
* Access control checks
* Comprehensive logging and monitoring

---

## 📐 System Architecture (High-Level)

```
Frontend (React)
        ↓
REST API Backend (Node.js / Express)
        ├── Satellite API Integration (N2YO)
        ├── OSINT Tool Runner (Python – Sherlock)
        ├── Rate Limiting & Logging
        ↓
Database (PostgreSQL / MongoDB)
```

---

## 🧠 Ethical & Legal Considerations

DataVeil is built with **ethics and legality as a core principle**:

✅ Only publicly available data is accessed
❌ No scraping of private or authenticated content
❌ No tracking of individuals without user-initiated input
❌ No automated profiling or decision-making

This project exists to:

* Educate users on **data exposure risks**
* Encourage **responsible security thinking**
* Demonstrate **defensive analysis techniques**

> **Important:**
> This tool should only be used for **educational, research, or defensive security purposes**.

---

## 📘 Status & Roadmap

**Current Status**

* Core architecture and feature design
* Frontend dashboard in progress
* Backend API integration planned

**Planned Enhancements**

* Alerting & notifications
* Improved exposure scoring models
* Report generation (PDF)
* Role-based access control
* Additional OSINT integrations

