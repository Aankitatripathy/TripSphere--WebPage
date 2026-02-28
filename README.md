# TripSphere. Travel Planning Web App

## Project Summary
TripSphere is a cloud-deployed travel planning web application built with ASP.NET Core MVC. It lets users create travel plans, book trips, submit feedback, and manage accounts. It is deployed on Microsoft Azure.

## Live Demo
Deployed URL
https://tripsphereweb-e5cjgpdvajbze2e8.westeurope-01.azurewebsites.net/

## Tech Stack

### Backend
- ASP.NET Core MVC (C#)
- Entity Framework Core
- SQL Server (Azure)

### Frontend
- Razor Views
- Bootstrap
- CSS Grid and Flexbox

### Cloud and DevOps
- Azure App Service
- GitHub Actions (CI/CD)

## APIs Used
- Weather API
- BookNow API
- ContactUs API

## Core Features
- Travel plan management: create and manage trips
- Booking flow: capture and store user trip details via BookNow API
- Feedback system: ratings, comments, and submission timestamps
- Contact module: store user inquiries in the database
- Authentication and role-based access
- Cloud deployment on Azure

## Data Model
The database is designed around three main tables and clear relationships.

### Tables

#### TravelMode
- Stores transport types (example: Flight)
- Key fields: Id (PK), ModeOfTransport
- Relationship: one TravelMode can be used by many TravelPlans

#### TravelPlans
- Stores trip details
- Key fields include: Id, Destination, Country, Duration, Budget, TravelModeId (FK)
- Relationships:
  - one TravelMode to many TravelPlans
  - one TravelPlan to many TravelFeedback entries

#### TravelFeedback
- Stores trip reviews and ratings
- Key fields include: FeedbackId (PK), Rating (1 to 5), Comments, SubmittedOn, TripId (FK)
- Relationship: one TravelPlan can have many TravelFeedback entries

## Security Notes
The project includes secure user interaction and authentication work, with protections against common issues like SQL injection and XSS. It uses JWT for API calls and cookie-based sessions for MVC pages.

## Repository Structure
Typical ASP.NET Core MVC structure:
- Controllers, Models, Views for MVC logic and UI
- Data and Migrations for EF Core database integration
- wwwroot for static assets (CSS, JS, images)

## How to Run Locally

### Prerequisites
- .NET SDK installed
- SQL Server (local) or Azure SQL connection string

### Steps
1. Clone the repo from GitHub.
2. Open the solution in Visual Studio.
3. Update the database connection string in `appsettings.json`.
4. Apply migrations (if migrations are included).
5. Run the project.

### CLI Option
```bash
dotnet restore
dotnet build
dotnet run
