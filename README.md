# Yatra Verse 🌏

> AI-Powered Tourism & Travel Platform for India

[![MIT License](https://img.shields.io/badge/License-MIT-orange.svg)](LICENSE)

Yatra Verse is a full-stack tourism platform that solves the biggest pain points of Indian travel:

- **Travel Buddy Matching** – AI-matched companions based on destination, dates, interests, budget & vibe
- **Local Hosts & Experiences** – Homestays, guides, food tours & hidden gems
- **Safety Intelligence** – Real-time weather, government alerts, road conditions & risk meter
- **Smart Maps** – Google Maps integration with hidden gems, hosts & nearby buddies
- **Multilingual PWA** – Installable, offline-ready, mobile-first

---

## 🧱 Tech Stack

**Frontend:** Next.js 14 (App Router), TypeScript, Tailwind CSS, Framer Motion, Shadcn-style UI, Zustand
**Backend:** Node.js, Express.js, MongoDB (Mongoose), Redis, JWT, Twilio, Nodemailer, Google OAuth
**Maps & APIs:** Google Maps, Google Places, OpenWeather, Government Alert APIs
**Deployment:** Vercel (frontend), Render/Railway (backend), MongoDB Atlas

---

## 📁 Project Structure

```
yatra-verse/
├── backend/
│   ├── src/
│   │   ├── config/         # DB & Redis
│   │   ├── controllers/    # Route handlers
│   │   ├── middleware/     # Auth, validation
│   │   ├── models/         # Mongoose schemas
│   │   ├── routes/         # Express routes
│   │   ├── utils/          # Helpers, seed
│   │   └── server.js       # Entry
│   ├── .env.example
│   ├── Dockerfile
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── app/            # Next.js pages (App Router)
│   │   ├── components/     # UI components
│   │   ├── lib/            # API client, utils
│   │   └── store/          # Zustand stores
│   ├── public/             # Static assets
│   ├── .env.example
│   ├── tailwind.config.ts
│   ├── next.config.mjs
│   └── package.json
├── docker-compose.yml
├── vercel.json
└── README.md
```

---

## 🚀 Local Setup

### Prerequisites
- Node.js 20+
- MongoDB (local or Atlas)
- Redis (optional, for caching)
- Google Maps API key

### 1. Clone & Install

```bash
git clone <repo-url> yatra-verse
cd yatra-verse

# Backend
cd backend
cp .env.example .env
npm install
npm run seed   # populates demo data

# Frontend
cd ../frontend
cp .env.example .env
npm install
```

### 2. Configure environment

`backend/.env`:
```env
MONGO_URI=mongodb://localhost:27017/yatraverse
JWT_SECRET=your_secret
GOOGLE_MAPS_API_KEY=...
WEATHER_API_KEY=...
GOOGLE_CLIENT_ID=...
TWILIO_ACCOUNT_SID=...
```

`frontend/.env.local`:
```env
NEXT_PUBLIC_API_URL=http://localhost:5000/api
NEXT_PUBLIC_GOOGLE_MAPS_KEY=...
NEXT_PUBLIC_GOOGLE_CLIENT_ID=...
```

### 3. Run

```bash
# Terminal 1
cd backend && npm run dev

# Terminal 2
cd frontend && npm run dev
```

Visit `http://localhost:3000`.

---

## 🐳 Docker (Full Stack)

```bash
docker-compose up --build
```

---

## ☁️ Deployment

### Backend → Render / Railway
1. Create new Web Service from `backend/`
2. Build: `npm install`
3. Start: `node src/server.js`
4. Add all env vars from `.env.example`

### Frontend → Vercel
1. Import repo into Vercel
2. Root directory: `frontend`
3. Build command: `next build`
4. Add env vars

### Database → MongoDB Atlas
1. Create cluster
2. Whitelist IP (0.0.0.0/0 for Render/Railway)
3. Copy connection string → `MONGO_URI`

### Google Maps
1. Enable: Maps JavaScript API, Places API, Geocoding API
2. Create API key, restrict to your domains

---

## 📡 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | Register user |
| POST | `/api/auth/login` | Email/password login |
| POST | `/api/auth/google` | Google OAuth |
| POST | `/api/auth/otp/send` | Send OTP |
| POST | `/api/auth/otp/verify` | Verify OTP |
| GET | `/api/buddy/search` | AI-matched buddies |
| GET | `/api/buddy/matches` | Your matches |
| POST | `/api/buddy/request` | Send match request |
| GET | `/api/hosts` | List experiences |
| POST | `/api/bookings` | Create booking |
| GET | `/api/bookings/my` | My bookings |
| GET | `/api/destinations` | List destinations |
| GET | `/api/destinations/nearby` | Nearby places |
| GET | `/api/alerts` | Safety alerts |
| GET | `/api/alerts/weather` | Weather |
| GET | `/api/alerts/safety` | Safety score |
| GET | `/api/reviews` | Reviews |
| POST | `/api/reviews` | Create review |
| GET | `/api/maps/places` | Google Places |
| GET | `/api/maps/directions` | Directions |

---

## 🗄 Database Models

- **User** – profile, verification, preferences
- **Host** – local experiences, pricing
- **Booking** – reservations, payments
- **Match** – buddy match requests
- **Review** – ratings & comments
- **Alert** – safety/government/weather
- **Destination** – places & hidden gems
- **Message** – chat
- **Notification** – user alerts

---

## 🤖 AI Match Score

Travel Buddy match score (0–100) based on:
- Destination overlap (25)
- Interest overlap (20)
- Travel style (15)
- Date overlap (15)
- Budget similarity (10)
- Language overlap (10)
- Verification bonus (5)

---

## 🎨 Design System

- **Colors:** Saffron `#f97316`, Indigo `#4f46e5`, Emerald, White
- **Animations:** Framer Motion
- **Glassmorphism:** `backdrop-filter: blur(12px)`
- **Responsive:** Mobile-first
- **PWA:** Installable, offline-ready

---

## 🌟 Bonus Features (Included)

✅ AI trip planner (recommend endpoint)
✅ AI narration for monuments (Web Speech API)
✅ Multilingual PWA
✅ Real-time safety score
✅ UPI/Razorpay ready (paymentMethod field)
✅ Hidden gems discovery

---

## 📜 License

MIT © 2026 Yatra Verse

---

## 🙏 Credits

Built with ❤️ for travelers, by travelers.

🇮🇳 **Incredible India, the smart way.**
