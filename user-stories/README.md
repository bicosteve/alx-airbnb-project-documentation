# User Stories

## User Story: User Registration

- Title: Register a new user account

### As a new user,

- I want to register an account using my first name, last name, email, phone number, and password,
- So that I can create an Airbnb profile and start using the platform.

### Acceptable Criteria

Scenario: Successful registration with valid input
Given I am on the registration page
When I enter a valid first name, last name, email, phone number, and password
And I click the "Register" button
Then my account should be created
And I should see a confirmation message or be redirected to the dashboard

Scenario: Registration with missing fields
Given I am on the registration page
When I submit the form with one or more fields left blank
Then I should see error messages indicating which fields are required

Scenario: Registration with an already registered email
Given another user already exists with the same email
When I try to register using that email
Then I should see an error message saying the email is already in use

Scenario: Registration with invalid email or phone format
Given I am on the registration page
When I enter an invalid email or phone number
Then I should see an error message explaining the format is incorrect

## User Story: User Login

- Title: Log in to an existing account

### As a registered user,

- I want to log in using my email and password,
- So that I can access my Airbnb account and manage my bookings or listings.

### Acceptable Criteria

Scenario: Successful login with valid credentials

Given I am on the login page
When I enter a registered email and the correct password
And I click the "Login" button
Then I should be logged in
And I should be redirected to my dashboard or home page

Scenario: Login with incorrect password
Given I am on the login page
When I enter a registered email and an incorrect password
And I click the "Login" button
Then I should see an error message indicating the password is incorrect

Scenario: Login with unregistered email
Given I am on the login page
When I enter an email that is not associated with any account
And I click the "Login" button
Then I should see an error message saying the email is not recognized

Scenario: Login with empty fields
Given I am on the login page
When I leave the email or password field empty
And I click the "Login" button
Then I should see validation messages for the required fields

## User Story: Make a Booking

- Title: Book a property

### As a registered user,

- I want to book a property by selecting dates and confirming the reservation,
- So that I can secure accommodation for my trip.

### Acceptable Creteria

Scenario: Successful booking of an available property
Given I am a logged-in user
And I am viewing a property's listing page
When I select valid check-in and check-out dates
And the property is available for those dates
And I click the "Book Now" or "Reserve" button
Then the booking should be created
And I should see a confirmation page with booking details

Scenario: Attempting to book with overlapping or unavailable dates
Given I am on a property's listing page
When I select dates that overlap with an existing booking
Then I should see a message that the property is not available for those dates

Scenario: Booking without being logged in
Given I am not logged in
When I try to book a property
Then I should be prompted to log in or sign up

Scenario: Booking with invalid or incomplete date selection
Given I am on a property's listing page
When I select an invalid date range or leave date fields empty
And I click the "Book Now" button
Then I should see a validation message asking me to select valid dates
