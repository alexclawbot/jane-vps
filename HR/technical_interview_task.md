# Technical Interview Task - Senior Full Stack Developer

**Candidate:** Nelya Parfenova  
**Position:** Senior Full Stack Developer  
**Company:** Advantage Plus  
**Date:** 

---

## About Advantage Plus

Advantage Plus is a premium lifestyle membership platform (PHP/Laravel 12 + Vue.js 3) serving the UAE market. Key technologies:
- Backend: PHP 8.3, Laravel 12.x, Node.js
- Frontend: Vue.js 3, Pinia, Nuxt
- Database: MariaDB 10.11, Redis 6.2, Elasticsearch 8.17.2
- Infrastructure: AWS, Docker, Kubernetes, GitLab CI/CD

---

## Task Overview

Build a simplified **Venue Booking System** — a core feature of the Advantage Plus platform.

### Time Allowance
- **90 minutes** for implementation
- **30 minutes** for code review and questions

---

## Requirements

### 1. Database Schema (Laravel Migrations)

Create migrations for:

```php
// venues table
- id (bigint, unsigned, primary key)
- name (string, 255)
- description (text, nullable)
- location (string, 255)
- capacity (integer)
- opening_time (time)
- closing_time (time)
- is_active (boolean, default true)
- created_at, updated_at

// bookings table
- id (bigint, unsigned, primary key)
- key → venue_id (foreign venues)
- member_id (bigint, unsigned)
- booking_date (date)
- booking_time (time)
- status (enum: pending, confirmed, cancelled, completed)
- guest_count (integer, default 1)
- notes (text, nullable)
- created_at, updated_at
```

### 2. Models & Relationships

- Define Eloquent models with relationships
- Add scopes for active venues, upcoming bookings
- Add validation rules

### 3. API Endpoints (RESTful)

Create these endpoints:

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/venues` | List all active venues |
| GET | `/api/venues/{id}` | Get venue details with availability |
| POST | `/api/bookings` | Create a new booking |
| GET | `/api/bookings/{id}` | Get booking details |
| PUT | `/api/bookings/{id}/cancel` | Cancel a booking |

### 4. Business Logic

- **Availability Check:** Venue must be open at booking time
- **Capacity Check:** Cannot exceed venue capacity
- **Double Booking Prevention:** Same venue + time = conflict
- **Cancellation:** Only pending/confirmed bookings can be cancelled

### 5. Basic Vue.js Component

Create a simple **VenueCard** component that displays:
- Venue name and location
- Capacity
- Operating hours
- "Book Now" button

---

## Evaluation Criteria

### Must Have (Pass/Fail)
- [ ] Migrations run without errors
- [ ] Models have correct relationships
- [ ] GET venues endpoint returns data
- [ ] POST booking creates record
- [ ] Availability logic prevents double-booking

### Should Have
- [ ] Proper validation with error messages
- [ ] Booking cancellation endpoint works
- [ ] Code follows Laravel conventions
- [ ] Basic Vue component renders

### Nice to Have
- [ ] Unit tests for business logic
- [ ] Booking conflict detection
- [ ] Additional API endpoints

---

## Questions (Verbal Discussion)

After the coding task, discuss:

1. **Architecture:** How would you scale this system to handle 10,000 concurrent bookings?
2. **Security:** What security considerations for payment processing in Laravel?
3. **DevOps:** How would you set up CI/CD for this Laravel application?
4. **Team:** How do you handle code reviews and mentor junior developers?

---

## Submission

Provide:
1. GitHub/GitLab repository link OR
2. ZIP file with all code

Include:
- Migration files
- Model files
- Controller files
- Routes definition
- Vue component (single file)
- Brief setup instructions

---

## Notes for Interviewer

**Nelya's Strengths to Explore:**
- Her AWS/CloudFormation experience → Ask about infrastructure-as-code
- SOC 2 compliance background → Ask about security best practices
- Microservices experience → Ask about scaling and distributed systems
- Leadership experience → Ask about team management approach

**Potential Gaps to Assess:**
- Laravel 12 specific features (if she's been on older versions)
- Vue.js 3 Composition API (if she mainly used Vue 2)
- Elasticsearch integration experience
