# DevEvent – Discover & Book Developer Events

A modern platform to explore, view, and book developer-focused events — including hackathons, conferences, meetups, and tech summits.

Built with **Next.js 16, React 19, Tailwind CSS, TypeScript, MongoDB, Cloudinary & PostHog**, DevEvent combines clean UI, fast APIs, analytics, and magical WebGL visuals.

---

## 🚀 Features

### 🔎 Explore Events
- Browse all featured dev events in a clean grid UI  
- View detailed event pages including:  
  - Description & Overview  
  - Event schedule and agenda  
  - Venue / mode (online, offline, hybrid)  
  - Audience & tags  
  - Organizer information  

### 🖼️ Image Uploads (Cloudinary)
- Event creation API handles file uploads  
- Images are uploaded to Cloudinary (`DevEvent` folder)  
- Returns a secure URL for the event banner

### 📝 Book Your Spot
- Simple email-based booking system  
- Validations & unique constraint: one booking per event per email  
- Stores bookings in MongoDB using Mongoose  
- Tracks bookings using PostHog analytics

### ✨ Similar Events Recommendation
- Recommendations based on event tags  
- Excludes the current event  
- Uses MongoDB filtering + indexing for performance

### 🎇 WebGL Light Rays Background
A fully custom **OGL-based WebGL animation** that adds:
- Dynamic reactive lighting  
- Mouse-follow effects  
- Smooth performance  
- Only runs when visible (IntersectionObserver optimized)

### ⚡ Modern Performance Features
- Next.js 16 App Router  
- React 19 server components  
- `cacheLife()` caching for event pages  
- Revalidated fetch for dynamic event details  
- Global MongoDB connection caching  

---

## 🛠️ Tech Stack

### Frontend
- Next.js 16 (App Router)
- React 19
- TypeScript
- Tailwind CSS v4
- OGL (WebGL animations)

### Backend
- Next.js API Routes
- MongoDB + Mongoose
- Cloudinary (image uploads)

### Analytics
- PostHog (client + server)

---

## 📁 Project Structure

/app
├── page.tsx → Homepage
├── layout.tsx → Fonts, Navbar, LightRays
├── api/events → Event APIs (create + fetch)
├── events/[slug] → Dynamic event page
/components
├── EventCard.tsx
├── EventDetails.tsx
├── BookEvent.tsx
├── LightRays.tsx
└── Navbar.tsx
/database
├── event.model.ts
└── booking.model.ts
/lib
├── mongodb.ts → DB connection caching
├── actions → Server actions
└── constants.ts → Static featured events
/public
├── images/ → Event images
└── icons/ → UI icons
