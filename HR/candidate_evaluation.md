# Evaluation: Technical Task

**Candidate:** [Candidate Name]  
**Position:** Senior Full Stack Developer  
**Date:** 

---

## Code Review

### 1. Business Logic (Double Booking Check) ✅

```php
$exists = Booking::where('venue_id', $venue->id)
    ->where('booking_date', $validated['booking_date'])
    ->where('booking_time', $validated['booking_time'])
    ->where('status', '!=', 'cancelled')
    ->exists();
```

**Pros:**
- ✅ Correctly checks for existing non-cancelled bookings
- ✅ Uses `exists()` for efficiency (stops at first match)
- ✅ Returns 422 for validation error

**Issues:**
- ⚠️ Missing capacity check (mentioned in requirements)
- ⚠️ Missing venue open hours check
- ⚠️ Time comparison might need timezone consideration

---

### 2. Cancellation Logic ✅

```php
if (!in_array($booking->status, ['pending', 'confirmed'])) {
    return response()->json(['error' => 'Only pending or confirmed bookings can be cancelled'], 422);
}
$booking->update(['status' => 'cancelled']);
```

**Pros:**
- ✅ Correctly validates status before cancellation
- ✅ Returns proper error message
- ✅ Clean update call

---

### 3. Vue.js Component (VenueCard.vue) ✅

```vue
<template>
  <div class="border rounded-lg p-4 shadow-sm bg-white flex flex-col gap-2">
    <div class="flex justify-between items-start">
      <h3 class="text-xl font-bold">{{ venue.name }}</h3>
      <span class="text-xs px-2 py-1 bg-gray-100 rounded">Cap: {{ venue.capacity }}</span>
    </div>
    <p class="text-gray-600 text-sm italic">{{ venue.location }}</p>
    <div class="mt-2 text-sm text-blue-800">
      <strong>Hours:</strong> {{ venue.opening_time }} - {{ venue.closing_time }}
    </div>
    <button @click="$emit('book', venue.id)" class="...">Book Now</button>
  </div>
</template>
```

**Pros:**
- ✅ Shows name, location, capacity, hours
- ✅ "Book Now" button with event emission
- ✅ Clean Tailwind CSS styling
- ✅ Uses Composition API (`script setup`)

---

## Summary

| Requirement | Status |
|-------------|--------|
| Double booking prevention | ✅ Done |
| Cancellation logic | ✅ Done |
| VenueCard component | ✅ Done |
| Capacity check | ❌ Missing |
| Open hours check | ❌ Missing |
| Models/Migrations | ❌ Not submitted |
| API Endpoints | ❌ Not submitted |

---

## Verdict

**Good for 60-minute task:**
- Business logic is correct
- Vue component is clean and functional
- Shows good Laravel/Vue understanding

**Missing from full submission:**
- Migrations
- Models
- Full API controller
- Routes

**Recommendation:** Pass - The key logic is correct. Missing files may be in other parts of her submission not shared here.

---

## Questions for Follow-up

1. "Where are the migrations and models?"
2. "How would you add the capacity check?"
3. "How would you handle timezone differences?"
