# HotelPro — End-to-End MERN Hotel Booking and Management System

HotelPro is a professional, secure, and fully responsive hospitality platform designed for hotel booking, guest management, room inventory, staff operations, and double-booking prevention.

## Tech Stack

- **Backend:** Node.js, Express.js, MongoDB (Mongoose), JWT Authentication, Express Rate Limit, bcryptjs.
- **Frontend:** React 18, React Router, Axios, Vite, and Tailwind CSS.
- **Testing:** Jest, Supertest (server integration tests).

## Features & Architecture

1. **Authentication & Authorization:** Secure registration and login with bcrypt password hashing and JWT tokens. Role-based access control (Guest, Staff, Admin).
2. **Hotel & Room Discovery:** Search hotels by location, name, and rating with detailed room inventories and pricing.
3. **Robust Booking Lifecycle:** Create bookings with price snapshots, date validation, and **concurrency-safe overlap checking** to prevent double-booking.
4. **Operations & Dashboard:** Admin/staff management for hotels, rooms, and bookings.
5. **Testing Suite:** Comprehensive integration and unit tests covering health checks, auth, hotel retrieval, booking creation, and double-booking prevention.

## Quick Start & Setup

### 1. Backend Setup
```bash
cd server
npm install
cp .env.example .env
# Configure MONGODB_URI and JWT_SECRET in .env
npm run seed   # Seeds sample users, hotels, and rooms
npm run dev    # Starts server on port 5000
```

### 2. Running Tests
```bash
cd server
npm test
```

## Client Setup
```bash
cd client
npm install
npm run dev    # Starts Vite on port 3000; /api requests proxy to localhost:5000
npm run build  # Creates the production bundle in client/dist
```

Configure the backend first (see Backend Setup) and ensure MongoDB is available before using API-backed pages. The client currently uses the Vite development proxy; production hosting must provide an equivalent `/api` reverse proxy.

## API Endpoints Overview

- **Auth:** `POST /api/v1/auth/register`, `POST /api/v1/auth/login`, `GET /api/v1/auth/me`
- **Hotels:** `GET /api/v1/hotels`, `GET /api/v1/hotels/:id`, `POST /api/v1/hotels` (Admin/Staff), `POST /api/v1/hotels/:id/rooms`
- **Bookings:** `GET /api/v1/bookings`, `POST /api/v1/bookings`, `GET /api/v1/bookings/:id`, `PUT /api/v1/bookings/:id/status`

## Demo Credentials (after seeding)
- **Admin:** `admin@hotelpro.com` / `password123`
- **Staff:** `staff@hotelpro.com` / `password123`
- **Guest:** `guest@hotelpro.com` / `password123`
