# Airline Booking System API

This project is an Airline Booking System API built with Django and Django REST Framework. It allows you to manage flights and passengers, including creating, retrieving, updating, and deleting records.

## Setup

To set up the project locally, follow these steps:

## Clone the repository:
   
   git clone https://github.com/Yvonne022/145353_airline_booking_system
## Create and activate a virtual environment

djangoenv\Scripts\activate

## Install Dependencies
pip install -r requirements.txt

## Run Migrations

python manage.py migrate

## Run the Development Server
python manage.py runserver

### Models

### Flight

The Flight model represents a flight in the system.

Fields:

flight_number: A unique identifier for the flight.

departure: The departure date and time.

arrival: The arrival date and time.

origin: The starting location of the flight.

destination: The ending location of the flight.

capacity: The maximum number of passengers.

### Passenger

The Passenger model represents a passenger associated with a flight.

Fields:

first_name: The first name of the passenger.

last_name: The last name of the passenger.

email: A unique email address for the passenger.

phone_number: The passenger's phone number.

flight: A foreign key linking the passenger to a specific flight.

### Serializers

### FlightSerializer

Purpose: Serializes the Flight model for API responses and handles input validation for creating and updating flights.

Fields: All fields from the Flight model are serialized.

### PassengerSerializer

Purpose: Serializes the Passenger model for API responses and handles input validation for creating and updating passengers.

Fields:

All fields from the Passenger model are serialized.

The flight field is serialized using the FlightSerializer in read-only mode.

### Views/Viewsets

### FlightViewSet

Purpose: Provides the standard list, create, retrieve, update, and destroy actions for the Flight model.

URL: /api/flights/

### PassengerViewSet

Purpose: Provides the standard list, create, retrieve, update, and destroy actions for the Passenger model.

URL: /api/passengers/

### Design Decisions

RESTful API Design: The API follows REST principles, ensuring a clear separation of concerns and scalability.

Django REST Framework: Utilized for its robust features, including serializers, viewsets, and routers, making the API development process efficient.

Foreign Key Relationship: The Passenger model has a foreign key relationship with the Flight model to enforce data integrity and maintain the relationship between passengers and their flights.

Unique Constraints: Unique constraints on fields like flight_number and email ensure the uniqueness of these records in the database.

Passenger Filtering: The Passenger viewset includes filtering options using Django Filter Backend. This allows clients to filter passengers based on the associated flight. For example, you can filter passengers by the flight field to retrieve passengers associated with a specific flight.
