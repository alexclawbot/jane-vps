# Technical Task - Senior Full Stack Developer

**Company:** Advantage Plus  
**Position:** Senior Full Stack Developer

---

## About Us

Advantage Plus is a premium lifestyle membership platform serving the UAE market.

**Our Tech Stack:**
- Backend: PHP/Laravel, Node.js, Python, or Go (your choice)
- Frontend: Vue.js 3
- Database: MySQL/MariaDB, Redis

---

## Your Task: Build a Venue Booking System

Build a simplified version of our core booking feature.

**Time:** 60 minutes  
**Tech Stack:** Your choice (pick what you're best at)

---

### Option A: Node.js + Vue.js
- Express.js or Fastify API
- Sequelize or Prisma ORM
- Vue.js 3 component

### Option B: Python + Vue.js
- Django or FastAPI
- Django ORM or SQLAlchemy
- Vue.js 3 component

### Option C: PHP + Vue.js
- Laravel
- Eloquent ORM
- Vue.js 3 component

---

## Requirements

### 1. Database

Create tables:
- **venues**: id, name, location, capacity, opening_time, closing_time, is_active
- **bookings**: id, venue_id, member_id, booking_date, booking_time, status, guest_count

### 2. API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | /api/venues | List all active venues |
| GET | /api/venues/{id} | Get venue details |
| POST | /api/bookings | Create a new booking |
| GET | /api/bookings/{id} | Get booking details |
| PUT | /api/bookings/{id}/cancel | Cancel a booking |

### 3. Business Logic

- Venue must be open at booking time
- Cannot exceed venue capacity
- Prevent double booking (same venue + time)
- Only pending/confirmed bookings can be cancelled

### 4. Vue.js Component

Create a **VenueCard** component displaying:
- Venue name and location
- Capacity
- Operating hours
- "Book Now" button

---

## Submission

Provide:
1. Migration/Schema files
2. Model files
3. Controller/Route files
4. Vue component
5. Brief setup instructions

Send as ZIP or repository link.
