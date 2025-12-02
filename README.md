# 🟦 DevEvent – Discover & Book Developer Events

DevEvent is a modern, full-stack platform to explore developer-focused events — hackathons, conferences, meetups, and tech summits — all in one place.

Built using **Next.js 16, React 19, TypeScript, Tailwind CSS, MongoDB, Cloudinary & PostHog**, the project focuses on clean UI, optimized APIs, and a premium WebGL visual experience.

---

## 🚀 Features

### 🔍 Event Discovery
- Browse all featured developer events
- View detailed event pages:
  - Description & overview  
  - Agenda items  
  - Location / venue  
  - Mode (online / offline / hybrid)  
  - Audience & organizer  
  - Tags and related events  

### 🏞️ Cloudinary Image Uploads
- Upload event banners using Cloudinary  
- Secure URLs fetched instantly  
- Stream API support for high-performance uploads  

### 📨 Booking System
- Visitors can book events using email  
- Validation + unique constraint (one booking per event per email)  
- Fully stored in MongoDB  
- PostHog analytics for tracking booking events  

### 🎯 Similar Event Recommendations
- Based on tags  
- Excludes current event  
- Optimized with MongoDB indexing  

### 🎇 WebGL Light Rays Background (OGL)
A custom animated background using OGL for:
- Dynamic rays  
- Mouse-follow interactivity  
- Smooth, GPU-accelerated animations  
- Auto-disable when off-screen (IntersectionObserver)  

### ⚡ Performance & Modern Architecture
- Next.js App Router (v16)
- React Server Components
- `cacheLife()` caching for pages
- Revalidated fetch for API responses
- Global MongoDB connection pooling  
- Tailwind CSS v4 with custom theme tokens

---

## 🛠️ Tech Stack

### Frontend
- **Next.js 16**
- **React 19**
- **TypeScript**
- **Tailwind CSS v4**
- **OGL (WebGL animation library)**

### Backend
- **MongoDB + Mongoose**
- **Next.js Route Handlers**
- **Cloudinary Upload API**

### Analytics
- **PostHog (client + server)**

---

## 📁 Project Structure

├── app/                                                                                                                                                                        
│ ├── page.tsx                                                                                                                                                                  
│ ├── layout.tsx                                                                                                                                                                
│ ├── globals.css                                                                                                                                                               
│ ├── api/                                                                                                                                                                      
│ │ └── events/ \
│ │ ├── route.ts \
│ │ └── [slug]/ \
│ │ └── route.ts \
│ └── events/ \
│ └── [slug]/ \
│ └── page.tsx \
├── components/ \
│ ├── EventCard.tsx \
│ ├── EventDetails.tsx \
│ ├── BookEvent.tsx \
│ ├── LightRays.tsx \
│ └── Navbar.tsx \
├── database/ \
│ ├── event.model.ts \
│ └── booking.model.ts \
├── lib/ \
│ ├── mongodb.ts \
│ ├── constants.ts \
│ ├── utils.ts \
│ └── actions/ \
│ ├── event.actions.ts \
│ └── booking.actions.ts \
├── public/ \
│ ├── images/ \
│ └── icons/ 

## 🔌 API Endpoints

### ➤ Create Event  
`POST /api/events`

Accepts `FormData`:

title
description
overview
location
venue
date
time
mode
audience
organizer
tags[] (JSON string)
agenda[] (JSON string)
image (File)

### ➤ Get All Events  

`GET /api/events`

---

### ➤ Get Event by Slug  
`GET /api/events/[slug]`

Example response:
```json
{
  "message": "Event fetched successfully",
  "event": { ... }
}
```

▶️ Getting Started
1. Clone Repo

`git clone https://github.com/YOUR_USERNAME/dev-events-nextjs16.git
cd dev-events-nextjs16`

2. Install Dependencies

`npm install`

Create .env.local

`MONGODB_URI=your_mongodb_uri \
NEXT_PUBLIC_BASE_URL=http://localhost:3000 \
NEXT_PUBLIC_POSTHOG_KEY=your_posthog_key \
CLOUDINARY_CLOUD_NAME=xxxx \
CLOUDINARY_API_KEY=xxxx \
CLOUDINARY_API_SECRET=xxxx`

Run Dev Server

`npm run dev`

