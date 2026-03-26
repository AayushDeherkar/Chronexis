Chronexis — Venture Risk Simulator

Simulate your startup before you build it. 800 Monte Carlo runs. Real probabilities. AI-powered insights.


What It Does
Chronexis lets founders stress-test their startup idea before writing a single line of product code. You enter your idea, team, deadline, and runway — and the system runs 800 probabilistic simulations powered by Google Gemini AI to tell you:

Will you ship on time?
Will you survive your runway?
Where are your biggest bottlenecks?
What are your top 10 tasks to start with?


Tech Stack
LayerTechnologyFrontendNext.js 14, React, TypeScript, Tailwind CSSBackendNode.js, Express, TypeScript, ts-node-devDatabaseMongoDB AtlasAIGoogle Gemini 2.5 Flash APIChartsRechartsFontsIBM Plex Mono, Barlow Condensed, DM SansFrontend HostingVercelBackend HostingRailway

How It Works

User fills in startup idea, target market, revenue model, team, deadline, and runway
Backend sends the idea to Gemini which generates 8–14 custom execution modules (e.g. "Auth System", "Payment Integration") each with complexity scores, uncertainty ratings, and risk drivers
800 Monte Carlo simulations run across those modules simulating different execution outcomes
Results are saved to MongoDB and displayed on a shareable results page
Gemini generates an executive summary, recommendations, and first 10 Day-1 tasks


Results Page Shows

On-time delivery probability
Runway survival probability
Finish day distribution histogram
Top failure modes breakdown
Critical path bottlenecks
Risk exposure heatmap
Role utilization / overload
AI executive summary
AI recommendations
First 10 priority tasks for Day 1



Local Setup
Prerequisites

Node.js v18+
A Google Gemini API key (free at aistudio.google.com)
A MongoDB Atlas cluster (free tier works)

1. Clone the repo
bashgit clone https://github.com/AayushDeherkar/Chronexis.git
cd Chronexis
2. Create environment files
Create backend/.env:
PORT=4000
MONGODB_URI=your_mongodb_connection_string
MONGODB_DB_NAME=cognitive-twin
GEMINI_API_KEY=your_gemini_api_key
FRONTEND_URL=http://localhost:3000
Create frontend/.env.local:
NEXT_PUBLIC_API_URL=http://localhost:4000
3. Install dependencies and run
Terminal 1 — Backend:
bashcd backend
npm install
npm run dev
Terminal 2 — Frontend:
bashcd frontend
npm install
npm run dev
4. Open the app
Go to http://localhost:3000

Deployment
Backend → Railway

Go to railway.app → New Project → Deploy from GitHub
Set Root Directory to backend
Set Start Command to npm run dev
Add all 5 environment variables in the Variables tab
Generate a domain in Settings → Networking

Frontend → Vercel

Go to vercel.com → New Project → Import repo
Set Root Directory to frontend
Set Framework to Next.js
Add environment variable: NEXT_PUBLIC_API_URL = your Railway URL
Deploy

After deploying both
Update FRONTEND_URL on Railway to your Vercel URL to fix CORS.

Design
Industrial Bloomberg terminal aesthetic — deep navy background (#03070f) with amber, cyan, and jade accents. IBM Plex Mono for data labels, Barlow Condensed for headlines, DM Sans for body text. Scan-line animation on page load.
