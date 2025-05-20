# Job Application Tracker & Tailoring Assistant

## Overview

The Job Application Tracker & Tailoring Assistant is a modern, browser-based tool that helps job seekers organize their job search, track applications visually, and use AI to improve their resumes and cover letters. It also supports company research, providing a comprehensive workflow for job applications.

---

## Product Manager Perspective

### What is it?
- **A single-page web app** for tracking job applications, optimizing application materials, and conducting company research.
- **Visual Kanban board** for managing applications through stages (To Apply, Applied, Follow-Up, Interview, Rejected, Offer), with drag-and-drop, color-coded status, and optimization indicators.
- **Dashboard** for pipeline stats, visual stat cards, and a prioritized list of upcoming follow-ups (with overdue/today highlights).
- **Tailoring Studio** for AI-powered resume/cover letter feedback, company research, and template management.
- **Settings** for configuring AI providers (local or cloud), managing resume and cover letter templates, and application preferences.

### Key Value Propositions
- **Centralizes job search management**: All applications, notes, research, and templates in one place.
- **Boosts application quality**: AI suggestions and reusable templates help users tailor materials to each job.
- **Prepares users for interviews**: Company research tools, reminders for follow-ups, and interview substatus tracking.
- **Flexible AI integration**: Supports both local (Ollama) and cloud (Google Gemini) LLMs.
- **Referral and interview tracking**: Track referrals (with contact info) and interview rounds/substatus for each application.

### Typical User Flow
1. Add job applications via the Kanban board (including referral and interview substatus if applicable).
2. Move applications through stages as you progress; edit any field at any time.
3. Use the Dashboard to see stat cards for each stage and a list of upcoming follow-ups (overdue/today highlighted).
4. In the Tailoring Studio, select a job and paste or insert from template your job description, resume, and cover letter.
5. Generate AI-powered suggestions to improve your materials.
6. Add or generate company research notes.
7. Save, edit, or delete resume and cover letter templates for future use.
8. Configure AI and app settings as needed.

---

## Engineer Perspective

### Architecture
- **Frontend-only SPA**: All logic, UI, and state management are in a single HTML file with embedded JavaScript and Tailwind CSS.
- **No backend required**: Data is stored in the browser's `localStorage`.
- **Modular JS functions**: For Kanban rendering, dashboard stats, LLM API calls, template management, and settings.
- **LLM integration**: Uses `fetch` to call either a local Ollama API or Google Gemini API for tailoring suggestions.

### Key Features & Implementation
- **Kanban Board**: Drag-and-drop, add/edit/delete jobs, search/filter, color-coded by status, optimization indicator (shows if resume, cover letter, and job description are attached), and visual tags for interview substatus and referrals.
- **Dashboard**: Stat cards for each stage, total active applications, and a list of up to 5 upcoming follow-ups (with overdue/today highlights and visual cues).
- **Tailoring Studio**: 
  - Dropdown to select a job.
  - Textareas for job description, resume, cover letter (with clear buttons).
  - Insert resume/cover letter from template, or save current as a new template.
  - Button to generate AI suggestions (calls LLM, displays markdown-formatted feedback).
  - Company research area with sample generation and debug info for research workflow.
- **Template Management**:
  - Save, edit, delete, and insert resume and cover letter templates from both Tailoring Studio and Settings.
  - Templates are stored in localStorage and available for quick reuse.
- **Referral & Interview Substatus Tracking**:
  - Add referral info (checkbox + contact field) to any job application.
  - Track interview substatus (Recruiter, Screening, Round 1-5) for jobs in the Interview stage; substatus is shown as a tag on Kanban cards.
- **Settings**: 
  - Choose LLM provider (Ollama or Gemini).
  - Enter API endpoints/keys.
  - Save settings to `localStorage`.
  - Manage resume and cover letter templates.
- **Data Persistence**: All job data, templates, and settings are saved locally; no server or authentication.

### How to Run/Use
1. **Clone or download the repo.**
2. **Open `jobTrackerApp.html` in any modern browser.**
3. **(Optional) For AI features:**
   - For Ollama: Install and run Ollama locally, pull a model (e.g., `llama3`), and ensure the endpoint in Settings matches your setup.
   - For Gemini: Obtain an API key from Google AI Studio, enter it in Settings.
4. **All data is saved in your browser.** No backend or signup required.
5. **To use templates:** Go to Settings or Tailoring Studio to add, edit, or insert resume/cover letter templates.
6. **To track referrals/interview rounds:** Use the job modal to add referral info or set interview substatus.

### Extensibility & Next Steps
- **Backend integration** (future): For multi-device sync, user accounts, and persistent storage.
- **Enhanced analytics**: More dashboard metrics, interview/offer tracking, and advanced analytics page.
- **File uploads**: Directly upload resumes/cover letters.
- **Better error handling**: More robust notifications and LLM error management.
- **Template management**: Expand to support more document types and sharing.
- **Referral/interview tracking**: Add reminders and analytics for referrals and interview rounds.
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

- All code and logic are in `jobTrackerApp.html`. 
