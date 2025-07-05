# Backend Requirements Specifications

## 1. User Authentication

- **Endpoint**: POST `/api/auth/register`
- **Input**: `{ email, password, full_name }`
- **Output**: `JWT token`
- **Validation**: Email format, password strength (min 8 chars)
- **Performance**: Response within 500ms

## 2. Property Management

- **Endpoints**:
  - GET `/api/properties`
  - POST `/api/properties`
  - PUT `/api/properties/:id`
- **Input**: `{ title, location, price, amenities[] }`
- **Output**: Property JSON object
- **Validation**: Unique titles, price > 0

## 3. Booking System

- **Endpoint**: POST `/api/bookings`
- **Input**: `{ property_id, user_id, check_in, check_out }`
- **Output**: `{ booking_id, status }`
- **Validation**: No double-bookings, valid dates
