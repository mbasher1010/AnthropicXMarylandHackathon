# 🐢 TerpPath

> **An AI scholarship coach built specifically for University of Maryland students.**
> Find UMD-internal awards, draft essays in your own voice, connect with professors who can nominate you, and never miss a deadline again.

Built for the *Build for Humanity* hackathon — Track 2: Campus Intelligence & Equity.

---

## Why TerpPath?

UMD students leave thousands of dollars on the table every year — not because they don't qualify for scholarships, but because:

- **UMD-internal scholarships are hidden.** They live on department pages, OMSE microsites, and honors college portals nobody knows to check.
- **Faculty-nominated awards (Goldwater, Boren, Udall, Fulbright) require a professor's letter** — and most students have no idea how to ask.
- **Generic AI essay tools sound like generic AI essays.** They don't know your story.
- **Deadlines collide with finals week.** A reminder the night before midterms isn't a reminder, it's a stressor.

TerpPath fixes all of that, for Terps specifically.

---

## ✨ Features

| Feature | What it does |
|---|---|
| 🧠 **Profile Builder** | Major, GPA, background, first-gen status, identity, interests — the foundation for every match. |
| 📄 **Essay Vault** | Upload past essays. Claude extracts your voice, themes, and lived experience so future drafts sound like *you*. |
| 🐢 **Terrapin Opportunity Radar** | Scrapes and indexes UMD-only scholarships (Banneker-Key, Clark School, BSOS, OMSE, honors college, departmental awards). Lower competition = higher win rate. |
| ✍️ **Essay Draft Assistant** | Given a prompt + your vault, drafts in your voice. You edit — not rewrite from scratch. |
| 📅 **Smart Calendar Sync** | Pushes deadlines to Google Calendar, but **avoids dropping reminders during UMD finals week** and suggests start dates based on your academic load. |
| 🧑‍🏫 **Professor Connection Engine** | For nomination-required awards, finds UMD faculty whose research aligns with your interests and drafts a personalized cold email. |
| 🤝 **Terp Alumni Network** | Surfaces UMD alumni who won the same scholarships and drafts Terp-to-Terp outreach for advice + winning submissions. |
| 💼 **Handshake Integration** | Pulls scholarship/fellowship postings from your existing Handshake account into one unified dashboard. |

---

## 🛠️ Tech Stack

- **Framework:** Next.js 14 (App Router) + TypeScript
- **Styling:** Tailwind CSS
- **AI:** Anthropic Claude API (`claude-sonnet-4-6`)
- **Database & Auth:** Supabase (Postgres + Auth + Storage)
- **Calendar:** Google Calendar API
- **File Parsing:** `pdf-parse` (PDFs), `mammoth` (DOCX)
- **Deployment:** Vercel

---

## 🚀 Getting Started

### 1. Clone & install

```bash
git clone https://github.com/<your-username>/terppath.git
cd terppath
npm install
```

### 2. Environment variables

Copy `.env.example` to `.env.local` and fill in:

```bash
cp .env.example .env.local
```

You'll need:

- `ANTHROPIC_API_KEY` — from [console.anthropic.com](https://console.anthropic.com)
- `NEXT_PUBLIC_SUPABASE_URL` / `NEXT_PUBLIC_SUPABASE_ANON_KEY` — from your [Supabase project](https://supabase.com)
- `GOOGLE_CLIENT_ID` / `GOOGLE_CLIENT_SECRET` — from [Google Cloud Console](https://console.cloud.google.com) (enable Calendar API)

### 3. Run the dev server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

---

## 📁 Project Structure

```
terppath/
├── app/
│   ├── page.tsx                  # Landing page
│   ├── dashboard/                # Main app dashboard
│   ├── profile/                  # Profile builder
│   ├── essays/                   # Essay vault + draft assistant
│   ├── scholarships/             # Matcher + Terrapin Opportunity Radar
│   ├── professors/               # Faculty connection engine
│   ├── calendar/                 # Calendar sync UI
│   └── api/                      # Backend API routes
│       ├── match-scholarships/   # Claude-powered matching
│       ├── draft-essay/          # Voice-aware draft generation
│       ├── extract-voice/        # Essay vault analysis
│       ├── professor-search/     # Faculty matching
│       └── calendar-sync/        # Google Calendar push
├── components/                   # Reusable UI
├── lib/
│   ├── claude.ts                 # Anthropic client
│   ├── supabase.ts               # Supabase client
│   └── calendar.ts               # Google Calendar helpers
├── data/
│   ├── umd-scholarships.json     # Curated UMD-internal scholarships
│   ├── umd-faculty.json          # UMD faculty + research interests
│   └── umd-academic-calendar.json# Finals weeks, breaks, registration
└── public/                       # Static assets
```

---

## 🗺️ Roadmap

- [x] Profile builder + essay vault
- [x] UMD scholarship matcher with fit scoring
- [x] Voice-aware essay drafting
- [x] Calendar sync with finals-week awareness
- [x] Professor connection engine
- [ ] Live Handshake OAuth integration
- [ ] Alumni outreach via LinkedIn API
- [ ] Mobile app (React Native)
- [ ] Expand beyond UMD (UMBC, Towson, etc.)

---

## 🤝 Contributing

Built by Terps, for Terps. PRs welcome — especially scholarship dataset contributions and faculty research mappings.

---

## 📜 License

MIT — see [LICENSE](./LICENSE).
