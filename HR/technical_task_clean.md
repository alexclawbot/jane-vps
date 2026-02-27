# Technical Task - Senior Full Stack Developer

**Company:** Advantage Plus  
**Position:** Senior Full Stack Developer

---

## About Us

Advantage Plus is a premium lifestyle membership platform (PHP/Laravel + Vue.js) serving the UAE market.

**Our Tech Stack:**
- Backend: PHP 8.3, Laravel 12.x
- Frontend: Vue.js 3, Pinia, Nuxt
- Database: MariaDB, Redis, Elasticsearch
- Infrastructure: AWS, Docker, GitLab CI/CD

---

## Your Task: Build a Venue Booking System

Build a simplified version of our core booking feature.

### Time: 60 minutes

---

### 1. Database (Laravel Migrations)

Create migrations for:

**venues table**
- id (bigint, primary key)
- name (string)
- description (text, nullable)
- location (string)
- capacity (integer)
- opening_time (time)
- closing_time (time)
- is_active (boolean, default true)
- timestamps

**bookings table**
- id (bigint, primary key)
- venue_id (foreign key to venues)
- member_id (bigint)
- booking_date (date)
- booking_time (time)
- status (enum: pending, confirmed, cancelled, completed)
- guest_count (integer, default 1)
- notes (text, nullable)
- timestamps

---

### 2. Models

- Create Eloquent models with relationships
- Add scopes for active venues, upcoming bookings

---

### 3. API Endpoints

Create these RESTful endpoints:

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | /api/venues | List all active venues |
| GET | /api/venues/{id} | Get venue details |
| POST | /api/bookings | Create a new booking |
| GET | /api/bookings/{id} | Get booking details |
| PUT | /api/bookings/{id}/cancel | Cancel a booking |

---

### 4. Business Logic

Implement these rules:

- **Availability:** Venue must be open at booking time
- **Capacity:** Cannot exceed venue capacity
- **Double Booking:** Prevent same venue + same time
- **Cancellation:** Only pending/confirmed bookings can be cancelled

---

### 5. Vue.js Component

Create a **VenueCard** component that displays:
- Venue name and location
- Capacity
- Operating hours
- "Book Now" button

---

## Submission

Provide:
1. Migration files
2. Model files
3. Controller files
4. Routes definition
5. Vue component
6. Brief setup instructions

Send as a ZIP file or GitHub/GitLab repository link.
