# DataDock-AI
AI-powered web content scraper &amp; organizer with local ChromaDB storage  ## Features - Download videos/images/links from any site - Local ChromaDB vector database for AI-searchable content

# DataDock AI

🚀 AI-powered web content scraper & organizer with local ChromaDB storage

## Features
- Download videos/images/links from any site
- Local ChromaDB vector database for AI-searchable content
- Direct video downloads (YouTube/Vimeo) via yt-dlp
- BeautifulSoup web scraping
- React/Vite PWA frontend
- Huginn workflow automation

## Tech Stack
- **Backend**: Python/Flask, ChromaDB, yt-dlp, BeautifulSoup
- **Frontend**: React/Vite PWA
- **Automation**: Huginn (Ruby)
- **AI**: DeepSeek R1, Stable Diffusion (optional)

## GitHub Codespace Setup
1. Open [GitHub Codespaces](https://github.com/codespaces)
2. Create new codespace for your DataDock-AI repo
3. Use this folder structure:

DataDock-AI/
├── backend/
│ ├── requirements.txt
│ └── backend.py
├── frontend/
│ ├── package.json
│ └── src/
├── .devcontainer/
│ └── devcontainer.json
└── README.md

4. Add to `.devcontainer/devcontainer.json`:
```json
{
  "name": "DataDock AI",
  "features": {
    "ghcr.io/devcontainers/features/python:1": {"version": "3.10"},
    "ghcr.io/devcontainers/features/node:1": {"version": "18"}
  },
  "forwardPorts": [5000, 3000],
  "postCreateCommand": "pip install -r backend/requirements.txt && cd frontend && npm install"
}
Backend Setup
Create backend/requirements.txt:
flask
chromadb
beautifulsoup4
yt-dlp
requests
Add backend/backend.py (use Python boilerplate from previous messages)
Frontend Setup
In terminal:
bash
cd frontend
npm create vite@latest . -- --template react
npm install axios vite-plugin-pwa

Add React components (see App.jsx example from previous messages)
Local Development
bash
# Backend
cd backend
python -m venv venv
source venv/bin/activate  # venv\Scripts\activate on Windows
pip install -r requirements.txt
python backend.py

# Frontend
cd ../frontend
npm run dev

Huginn Automation
Install Ruby: ruby-lang.org
Follow manual install: Huginn docs
Use WebhookAgent to connect:
Trigger scrape via HTTP POST to localhost:5000/scrape
Pass URL parameters in request body
Usage
Launch PWA at localhost:3000
Enter target URL
Backend scrapes/downloads to downloads/ folder
Metadata searchable via ChromaDB in PWA
