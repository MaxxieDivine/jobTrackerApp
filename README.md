# Job Application Tracker & Tailoring Assistant

## Overview

The Job Application Tracker & Tailoring Assistant is a modern, browser-based tool that helps job seekers organize their job search, track applications visually, and use AI to improve their resumes and cover letters. It also supports company research, providing a comprehensive workflow for job applications.

---

## Product Manager Perspective

### What is it?
- **A single-page web app** for tracking job applications, optimizing application materials, and conducting company research.
- **Visual Kanban board** for managing applications through stages (To Apply, Applied, Follow-Up, Interview, Rejected, Offer).
- **Dashboard** for pipeline stats and upcoming follow-ups.
- **Tailoring Studio** for AI-powered resume/cover letter feedback and company research.
- **Settings** for configuring AI providers (local or cloud).

### Key Value Propositions
- **Centralizes job search management**: All applications, notes, and research in one place.
- **Boosts application quality**: AI suggestions help users tailor materials to each job.
- **Prepares users for interviews**: Company research tools and reminders for follow-ups.
- **Flexible AI integration**: Supports both local (Ollama) and cloud (Google Gemini) LLMs.
- **Company Research by Tavily AI: Supports company research provided by Tavily AI and refined by Google Gemini (2.0 flash).

### Typical User Flow
1. Add job applications via the Kanban board.
2. Move applications through stages as you progress.
3. Use the Dashboard to see stats and upcoming tasks.
4. In the Tailoring Studio, select a job and paste your job description, resume, and cover letter.
5. Generate AI-powered suggestions to improve your materials.
6. Add or generate company research notes.
7. Configure AI settings as needed.

---

## Engineer Perspective

### Architecture
- **Frontend-only SPA**: All logic, UI, and state management are in a single HTML file with embedded JavaScript and Tailwind CSS.
- **No backend required**: Data is stored in the browser's `localStorage`.
- **Modular JS functions**: For Kanban rendering, dashboard stats, LLM API calls, and settings management.
- **LLM integration**: Uses `fetch` to call either a local Ollama API or Google Gemini API for tailoring suggestions.

### Key Features & Implementation
- **Kanban Board**: Drag-and-drop, add/edit/delete jobs, search/filter, color-coded by status.
- **Dashboard**: Stat cards for each stage, list of upcoming follow-ups (with overdue/today highlights).
- **Tailoring Studio**: 
  - Dropdown to select a job.
  - Textareas for job description, resume, cover letter.
  - Button to generate AI suggestions (calls LLM, displays markdown-formatted feedback).
  - Company research area with sample generation and debug info for research workflow.
- **Settings**: 
  - Choose LLM provider (Ollama or Gemini).
  - Enter API endpoints/keys.
  - Save settings to `localStorage`.
- **Data Persistence**: All job data and settings are saved locally; no server or authentication.

### How to Run/Use
1. **Clone or download the repo.**
2. **Open `jobTrackerApp.html` in any modern browser.**
3. **(Optional) For AI features:**
   - For Ollama: Install and run Ollama locally, pull a model (e.g., `llama3`), and ensure the endpoint in Settings matches your setup.
   - For Gemini: Obtain an API key from Google AI Studio, enter it in Settings.
   - For Tavily: Obtain an API key from Tavily AI. (this is for the company research).
4. **All data is saved in your browser.** No backend or signup required.

### Extensibility & Next Steps
- **Backend integration** (future): For multi-device sync, user accounts, and persistent storage.
- **Enhanced analytics**: More dashboard metrics, interview/offer tracking.
- **File uploads**: Directly upload resumes/cover letters.
- **Better error handling**: More robust notifications and LLM error management.
- **Testing**: Add unit and E2E tests as complexity grows.

---

## Quick Start

```sh
# 1. Download or clone the repository
git clone https://github.com/YOUR-USERNAME/job-tracker-app.git
cd job-tracker-app

# 2. Open the app
# Just double-click jobTrackerApp.html or open it in your browser
```

---

## Documentation

- See the `Documentation/` folder for product requirements, sample research logs, and best practices.
- All code and logic are in `jobTrackerApp.html`. 
