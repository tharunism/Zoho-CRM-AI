# ⚡ NovaCRM — AI-Powered CRM Dashboard

> A production-grade CRM platform with real-time AI assistance, drag-and-drop pipeline management, and intelligent lead scoring — built with React and Claude AI.

[![React](https://img.shields.io/badge/React-18.2-61DAFB?style=flat&logo=react)](https://react.dev)
[![Vite](https://img.shields.io/badge/Vite-5.2-646CFF?style=flat&logo=vite)](https://vitejs.dev)
[![Claude AI](https://img.shields.io/badge/Claude-Sonnet_4-CC785C?style=flat)](https://anthropic.com)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat)](LICENSE)

---

## 🎯 Why This Project?

Zoho CRM is one of the most powerful sales platforms in the world. This project is my interpretation of what the **next generation of CRM** could look like — one where AI is not a bolt-on feature but the core intelligence layer that helps sales teams prioritize, communicate, and close faster.

Built as a portfolio project to demonstrate full-stack product thinking aligned with Zoho's domain.

---

## ✨ Features

### 📊 Dashboard
- Real-time KPIs: total pipeline value, hot leads count, revenue closed, average AI score
- Monthly revenue bar chart (last 7 months)
- Recent activity feed with live status indicators
- Proactive AI insight card highlighting the highest-priority action

### 👥 Lead Management
- Full leads table with search and filter (Hot / Warm / Cold)
- AI Score column with animated progress bars and color-coded thresholds
- Click-to-expand detail panel for any lead
- Contextual AI suggestion per lead (high/medium/low intent logic)

### 🔀 Sales Pipeline (Kanban)
- Drag-and-drop deal cards across pipeline stages
- Stages: Initial Contact → Discovery → Proposal → Negotiation → Closed Won
- Per-stage deal count and total value calculations
- Color-coded stage headers with visual drag-over feedback

### 📈 Analytics
- Conversion rate, average deal size, total leads, and closed deals summary
- Revenue trend chart (month-over-month)
- Lead source breakdown with horizontal bar visualization
- Lead score distribution heatmap across all contacts

### 🤖 AI Assistant (Claude-Powered)
- Real chat interface connected to **Anthropic's Claude Sonnet API**
- Fully context-aware — has access to all your pipeline data
- Quick-prompt buttons for common actions
- Capabilities:
  - Lead prioritization ("Which leads should I focus on today?")
  - Email drafting ("Write a follow-up for Deepika Rao")
  - Pipeline forecasting ("What's my close probability this week?")
  - Strategy advice ("Which deal is most likely to churn?")

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | React 18 + Vite 5 |
| Styling | Pure CSS with CSS Variables (no Tailwind) |
| AI Integration | Anthropic Claude Sonnet API |
| State Management | React useState / component state |
| Data | Mock data (easily replaceable with REST/GraphQL) |
| Charts | Custom SVG-free CSS bar charts |
| Drag & Drop | Native HTML5 Drag & Drop API |

---

## 🚀 Getting Started

### Prerequisites
- Node.js 18+
- An Anthropic API key (for the AI Assistant feature)

### Installation

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/novacrm-ai.git
cd novacrm-ai

# Install dependencies
npm install

# Start the development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### AI Assistant Setup

The AI Assistant requires an Anthropic API key. For security, **never commit your API key**.

**Option 1 — Environment Variable (recommended)**

Create a `.env` file in the project root:
```env
VITE_ANTHROPIC_API_KEY=sk-ant-...your-key-here...
```

Then update `AIAssistant.jsx` to read it:
```js
headers: {
  "x-api-key": import.meta.env.VITE_ANTHROPIC_API_KEY,
  ...
}
```

**Option 2 — Backend Proxy (production)**

For production use, route API calls through your own backend to keep keys secure.

---

## 📁 Project Structure

```
novacrm-ai/
├── src/
│   ├── components/
│   │   ├── Dashboard.jsx      # KPI cards, charts, activity feed
│   │   ├── LeadsTable.jsx     # Searchable, filterable lead list
│   │   ├── Pipeline.jsx       # Kanban board with drag-and-drop
│   │   ├── Analytics.jsx      # Revenue trends, source breakdown
│   │   └── AIAssistant.jsx    # Claude-powered chat interface
│   ├── data/
│   │   └── mockData.js        # Sample CRM data (8 leads, pipeline, charts)
│   ├── App.jsx                # Root component, sidebar navigation
│   ├── main.jsx               # React entry point
│   └── index.css              # Global styles, design system
├── index.html
├── vite.config.js
└── package.json
```

---

## 🧠 Architecture Decisions

### Why no Redux or external state management?
For a CRM of this scale, React's built-in state is sufficient and keeps the codebase readable. In a production app, I'd introduce Zustand or React Query for server state.

### Why pure CSS over Tailwind?
Demonstrates CSS fundamentals — specifically important for enterprise software like Zoho's products which rely on deeply customized design systems, not utility classes.

### Why Claude API directly from the frontend?
For a portfolio demo, this keeps the setup simple. In a real product, you'd proxy through a Node.js/Express backend to protect the API key and add rate limiting.

### AI Score Logic
In this demo, AI scores are mock values. In production, this would be a ML model trained on signals like:
- Email open/reply rates
- Website visit frequency & depth
- Time since last interaction
- Deal size relative to company size
- Stage velocity (how fast they moved through previous stages)

---

## 📊 Data Model

```js
// Lead object structure
{
  id: Number,
  name: String,
  company: String,
  email: String,
  phone: String,
  status: "Hot" | "Warm" | "Cold",
  score: Number,        // 0-100 AI-generated score
  value: Number,        // Deal value in INR
  stage: String,        // Current pipeline stage
  source: String,       // Acquisition channel
  lastActivity: String, // ISO date
  owner: String         // Sales rep name
}
```

---

## 🗺️ Roadmap

- [ ] Backend API with Node.js + Express
- [ ] PostgreSQL integration (replace mock data)
- [ ] JWT authentication + role-based access
- [ ] Email integration (send follow-ups directly from AI suggestions)
- [ ] Real ML-based lead scoring (scikit-learn or TensorFlow.js)
- [ ] WhatsApp Business API integration for outreach
- [ ] Mobile-responsive layout
- [ ] Export to CSV / PDF reports
- [ ] Webhook support for Zoho CRM / HubSpot sync

---

## 👤 About

Built by **N. Tharun** — B.Tech Computer Science & Engineering, Saveetha School of Engineering (2025).

Passionate about building products that combine clean engineering with real business value. Interested in SaaS, AI integration, and full-stack development.

- 📧 [your.email@example.com](mailto:your.email@example.com)
- 💼 [LinkedIn](https://linkedin.com/in/yourprofile)
- 🐙 [GitHub](https://github.com/yourusername)

---

## 📄 License

MIT License — feel free to use this as inspiration for your own projects.

---

> *"The best CRM is one your sales team actually wants to use."*
