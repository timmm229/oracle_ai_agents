# Oracle AI Agent Hub

AI-powered agents for Oracle ERP & EPM workflows. Built with Node.js/Express and the Anthropic Claude API.

## Agents

| Agent | Status | Description |
|-------|--------|-------------|
| Document Q&A | ✅ Live | Upload docs and ask questions — AI answers from your content |
| GL Data Analyzer | 🔜 Coming | Variance detection on trial balance exports |
| Data Quality Checker | 🔜 Coming | Validate COA and dimension mappings |
| Report Builder | 🔜 Coming | Generate formatted EPM reports |
| Mapping Assistant | 🔜 Coming | AI-assisted dimension mapping |
| Workflow Monitor | 🔜 Coming | Integration job monitoring and diagnostics |

## Quick Start (Local)

```bash
# Clone the repo
git clone <your-repo-url>
cd oracle-ai-agents

# Install dependencies
npm install

# Set your Anthropic API key
export ANTHROPIC_API_KEY=sk-ant-...

# Start the server
npm start
```

Open http://localhost:3000

## Deploy to Render

1. Push this repo to GitHub
2. Go to [render.com](https://render.com) → New → Web Service
3. Connect your GitHub repo
4. Render will detect `render.yaml` automatically
5. Add your `ANTHROPIC_API_KEY` in Environment → Secret Files or Env Vars
6. Deploy!

Alternatively, use the **Blueprint** method:
- Go to Render → New → Blueprint
- Point to your repo — Render reads `render.yaml` and sets everything up

## Project Structure

```
oracle-ai-agents/
├── server.js              # Express server + API proxy
├── package.json
├── render.yaml            # Render deployment config
├── public/
│   ├── index.html         # Agent Hub landing page
│   └── document-qa.html   # Document Q&A agent
└── README.md
```

## Architecture

- **Frontend**: Vanilla HTML/CSS/JS (no build step needed)
- **Backend**: Express server proxies requests to Anthropic API
- **Security**: API key stays server-side, never exposed to the browser
- **Deployment**: Render free tier (Node.js web service)

## Adding New Agents

1. Create a new HTML file in `public/` (e.g., `public/gl-analyzer.html`)
2. Add an API endpoint in `server.js` if the agent needs custom logic
3. Update the hub page (`public/index.html`) to link to the new agent
4. Update the card from "COMING SOON" to "LIVE"

---

*Built with [Claude](https://www.anthropic.com) · Not affiliated with Oracle Corporation*
