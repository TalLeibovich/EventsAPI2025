
# Event Management System API

This project is a Web API built with ASP.NET Core and Entity Framework Core for managing events and user registrations. It was developed as part of a backend programming course (Part A – server side only).

## Overview

The system allows:
- Managing users (create, read, update, delete)
- Creating and editing events with location, dates, and max capacity
- Registering users to events with validation
- Retrieving event schedule
- Integrating weather information (with caching) for event location and date

## Technologies

- .NET 8 (ASP.NET Core Web API)
- Entity Framework Core
- SQL Server
- Postman (for testing)
- Caching (in-memory)

## Database

The system uses a SQL Server database named `Events`, created using the `Database.sql` script.

Main tables:
- `Users` – stores user data
- `Events` – stores event information
- `EventUser` – many-to-many link between users and events (registrations)

All foreign key constraints and default values are defined in the script.

## Project Structure

- `Models/` – Entity classes (`User`, `Event`, `EventUser`)
- `EventsContext.cs` – DbContext for EF Core
- `Controllers/` – API endpoints for users, events, registrations, weather

The code is organized using a basic layered architecture, following best practices for small to mid-sized APIs.

## How to Run

1. Create a local SQL Server database named `Events`.
2. Run `Database.sql` to create the schema.
3. Open the solution in Visual Studio and run the API project.
4. Use Postman to send requests using the provided collection:
   - `EventsAPI_Collection.postman_collection.json`

## Testing

The Postman collection includes requests for all endpoints with validation tests (status codes, response fields, etc).  
All major flows are covered, including user creation, event registration, and weather retrieval.

## Notes

- Weather data includes simple caching to avoid unnecessary external API calls.
- Connection string is set for local development – adjust it as needed.
- This version covers Part A only (server side).

## Author

Developed by Tal Lei  
Creative approach to user-event registration, focused on clean design and reliable logic.
