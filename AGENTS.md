# AGENTS.md — Yatra Verse

## Build / Run / Test

### Backend
```bash
cd backend
npm install
cp .env.example .env       # then edit secrets
npm run dev                # http://localhost:5000
npm run seed               # populates demo users/destinations/hosts
npm start                  # production
```

### Frontend
```bash
cd frontend
npm install
cp .env.example .env.local
npm run dev                # http://localhost:3000
npm run build && npm start
```

### Docker
```bash
docker-compose up --build
```

## Testing
No test suite is bundled. Add `vitest` or `jest` per module if needed.

## Lint
```bash
cd frontend && npm run lint
```

## Conventions
- Frontend: App Router (`src/app/...`), client components marked `'use client'`, Tailwind for styling, framer-motion for animation.
- Backend: ES modules (`"type": "module"`), controllers → routes → server.js. Always use `protect` middleware for authenticated routes.
- Models live in `backend/src/models/` and use Mongoose.
- API client is `frontend/src/lib/api.ts` (Axios + JWT interceptor).

## Key files
- `backend/src/utils/matching.js` — AI match score algorithm
- `backend/src/controllers/alertController.js` — safety score & weather
- `frontend/src/app/safety/page.tsx` — safety dashboard UI
- `frontend/src/app/buddy/page.tsx` — travel buddy matcher UI
