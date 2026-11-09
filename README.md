# SoulNest — Mental Well-being Portal

SoulNest is a simple Next.js (React + TypeScript) starter. The landing page contains only:
- **Create account**
- **Already have an account? Log in**

## Requirements
- Node.js 20.9 or newer
- npm

## Run locally
```bash
npm install
cp .env.example .env.local
npm run dev
```
Open http://localhost:3000.

## Pages
- `/` — minimal landing page
- `/signup` — create-account form
- `/login` — login form

## API routes
- `POST /api/auth/register` — demo registration
- `POST /api/auth/login` — demo login
- `POST /api/ai/chat` — AI well-being companion endpoint

Example AI request:
```bash
curl -X POST http://localhost:3000/api/ai/chat \\
  -H "Content-Type: application/json" \\
  -d '{"message":"I feel stressed about my exams. Can you suggest a simple grounding exercise?"}'
```

To enable AI, add your key to `.env.local`:
```env
OPENAI_API_KEY=your_key_here
OPENAI_MODEL=gpt-4o-mini
```
Keep the key on the server. Never expose it in a `NEXT_PUBLIC_` variable or commit `.env.local`.

## Important before real deployment
This is a **student-project starter**, not production-ready authentication or clinical care:
- Demo accounts are stored in server memory and disappear when the server restarts.
- Demo passwords are not hashed and there are no secure sessions.
- Replace the demo auth routes with a database, password hashing (e.g. Argon2/bcrypt), session cookies, rate limiting, and input validation.
- Add a clear privacy notice and avoid collecting unnecessary sensitive information.
- The AI endpoint is for general supportive conversation only. It must not diagnose, provide treatment, or be presented as a therapist or emergency service. Add appropriate safeguarding, moderation, and human-support pathways before real users use it.
