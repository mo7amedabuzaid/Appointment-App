# Doctor Appointment Booking App 🩺

A full-stack platform where patients can browse doctors by specialty, view their details, and book appointments online. Built with **Next.js** and **Strapi 5**, with secure authentication powered by **Kinde**.

## Features

- Browse doctors with specialty, years of experience, address, and phone
- Filter doctors by category (sidebar and category cards)
- Doctor details page with an "About" section and suggested doctors
- Book an appointment by picking a date from a calendar and an available time slot
- Secure sign-in / sign-up with Kinde
- **My Booking** page with *Upcoming* and *Past* tabs
- Cancel upcoming appointments with a confirmation dialog and toast feedback
- Responsive UI built with Tailwind CSS and shadcn/ui

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Next.js 16 (App Router), React 19 |
| Styling | Tailwind CSS 4, shadcn/ui, Base UI, tw-animate-css |
| Auth | Kinde (`@kinde-oss/kinde-auth-nextjs`) |
| Backend | Strapi 5 (Headless CMS, REST API) |
| HTTP client | Axios |
| UI utilities | react-day-picker, date-fns, cmdk, lucide-react |

## Project Structure

```
├── appointment_app/        # Next.js frontend
│   └── app/
│       ├── _component/     # Header, Hero, Footer, CategorySearch, DoctorList
│       ├── _Utils/Api.js   # Axios API layer (Strapi)
│       ├── api/auth/       # Kinde auth route
│       ├── details/[id]/   # Doctor details + booking dialog
│       ├── search/[cname]/ # Doctors filtered by category
│       └── myBooking/      # User bookings (upcoming / past)
└── backend/                # Strapi 5 backend
```

## Strapi Content Types

| Collection | Fields |
|---|---|
| `doctors` | name, year_of_experience, address, phone, about, img (media), categroy (relation) |
| `categroys` | name, icon (media) |
| `appointments` | userName, email, date, time, doctor (relation) |

> Enable **find** and **findOne** for `doctors` and `categroys`, and **find**, **create**, **delete** for `appointments`, under *Settings → Users & Permissions → Public*.

## Getting Started

### Prerequisites

- Node.js 20+
- A [Kinde](https://kinde.com) account and application

### 1. Backend

```bash
cd backend
npm install
cp .env.example .env
npm run develop
```

Admin panel: http://localhost:1337/admin

### 2. Frontend

```bash
cd appointment_app
npm install
npm run dev
```

App: http://localhost:3000

### Environment Variables (`appointment_app/.env.local`)

```env
KINDE_CLIENT_ID=your_client_id
KINDE_CLIENT_SECRET=your_client_secret
KINDE_ISSUER_URL=https://your-domain.kinde.com
KINDE_SITE_URL=http://localhost:3000
KINDE_POST_LOGOUT_REDIRECT_URL=http://localhost:3000
KINDE_POST_LOGIN_REDIRECT_URL=http://localhost:3000
```

In the Kinde dashboard, add `http://localhost:3000/api/auth/kinde_callback` as an allowed callback URL.

## Scripts

| Command | Description |
|---|---|
| `npm run dev` | Start the Next.js dev server |
| `npm run build` | Production build |
| `npm run start` | Run the production build |
| `npm run lint` | Run ESLint |

## Author

**Mohamed Abuzaid** — [GitHub](https://github.com/mo7amedabuzaid)
