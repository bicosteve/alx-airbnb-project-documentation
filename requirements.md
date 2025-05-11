# Specification Requirement

1. Functional Requirements

## 1.1. User Registration

### Input Fields:

- First Name (Required)
- Last Name (Required)
- Email Address (Required, Unique)
- Phone Number (Optional, Unique)
- Password (Required, Minimum 8 characters, at least one number and one special character)

### Process:

- Validate all input fields.
- Check for uniqueness of email and phone number.
- Hash the password using a secure hashing algorithm (e.g., bcrypt).
- Store the user data in the User table.

### Output:

- Success message with user ID.
- Error message if validation fails or email/phone already exists.

## 1.2. User Login

### Input Fields:

- Email
- Password

### Process:

- Validate email and password.
- Retrieve user by email.
- Compare hashed password with stored hash.
- Generate and return an authentication token (e.g., JWT).

### Output:

-Success message with token.

- Error message on failure.

### Endpoints

- POST /api/register: Registers a new user.
- POST /api/login: Authenticates a user and returns a token.
- GET /api/user/{id}: Retrieves user profile (authenticated access only).

## 2.1 Property Management.

### 2.1. Property Attributes

- property_id UUID Primary Key, Unique Identifier
- name VARCHAR Name of the property
- host_id UUID Foreign Key referencing the User table
- location VARCHAR Physical address or general location
- description TEXT Detailed description of the property
- created_at TIMESTAMP Timestamp when the property was created
- updated_at TIMESTAMP Timestamp when the property was last updated

### API Endpoints

- POST /api/properties
- Description: Create a new property listing.

- GET /api/properties
- Description: Retrieve a list of all properties.
- Query Parameters (optional):
- host_id: Filter by host
- location: Filter by location

- GET /api/properties/{property_id}
- Description: Retrieve details of a specific property.
- PUT /api/properties/{property_id}
- Description: Update an existing property.
- DELETE /api/properties/{property_id}
- Description: Delete a property listing.

## 3.1. Booking System Requirement Specification

- The Booking System will serve customers, administrators, and service providers. It will provide a user-friendly interface for booking and managing reservations.

### 3.2 Service Search and Availability

- Users will be able to search for services based on various criteria (e.g., location, date, type).
- The system shall display available services based on user search criteria.
- Users shall be able to filter search results by price, rating, and location.

### 3.3 Booking Process

- Users will be able to select a service and view detailed information.
- Users will be able to book a service by providing necessary details (e.g., dates, number of guests).
- The system will calculate the total cost and display it before confirmation.
- Users will receive a confirmation SMS upon successful booking.

### 3.4 Payment Processing

- Users shall be able to make payments using credit/debit cards and other payment methods.
- The system shall securely process payments and store transaction details.

### 3.5 Booking Management

- Users shall be able to view their booking history.
- Users shall be able to modify or cancel their bookings within specified policies.
- Administrators shall be able to manage bookings and view statistics.

### 3.6 Review and Feedback

- Users shall be able to leave reviews and ratings for services they have booked.
- The system shall display user reviews on service detail pages.
