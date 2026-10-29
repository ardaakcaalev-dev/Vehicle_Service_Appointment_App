# AutoService - Vehicle Service Appointment App

An Android application that connects vehicle owners with mechanics for service appointments. Built with Java, Room (SQLite), and Retrofit.

## What It Does

The app has two roles — **Customer** and **Mechanic** — each with their own dashboard and workflows.

### Customer Features
- **Vehicle Management** — Add and manage vehicles with make/model data pulled from the NHTSA API
- **Browse Mechanics** — View mechanic profiles filtered by specialization (engine, electrical, transmission, brakes, etc.), with ratings and reviews
- **Book Appointments** — Schedule service appointments for a specific vehicle and service category
- **Dashboard** — Per-vehicle stats including total services, last oil change date, and a pie chart breakdown of service categories
- **Service History** — View completed service records per vehicle
- **Rate & Review** — Leave ratings and feedback after completed appointments
- **Messaging** — In-app chat with mechanics

### Mechanic Features
- **Pending Requests** — View and approve/reject incoming appointment requests
- **Appointment Management** — Track appointments through their lifecycle (pending, approved, in-progress, completed)
- **Appointment Details** — Add notes and update status on individual appointments
- **Messaging** — In-app chat with customers

### Shared
- **Authentication** — Register/login with role selection, passwords hashed locally
- **Settings** — User preferences and account management
- **Chat System** — Real-time-style messaging between customers and mechanics

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Java 11 |
| UI | Material Design Components, XML Layouts |
| Database | Room (SQLite) |
| Networking | Retrofit + OkHttp (NHTSA Vehicle API) |
| Charts | MPAndroidChart |
| Architecture | Activity-based, DAO pattern |
| Min SDK | 29 (Android 10) |
| Target SDK | 36 |

## Project Structure

```
app/src/main/java/com/example/mobile_project/
├── data/
│   ├── api/          # Retrofit service for NHTSA vehicle data
│   ├── dao/          # Room DAOs (User, Vehicle, Appointment, Message, Review, MechanicProfile)
│   ├── database/     # Room database singleton
│   ├── entity/       # Room entities
│   ├── model/        # Joined query models (AppointmentWithDetails, MechanicWithUser, etc.)
│   └── preferences/  # SharedPreferences session manager
├── ui/
│   ├── auth/         # Login & Registration
│   ├── common/       # Chat, Settings (shared between roles)
│   ├── customer/     # Customer dashboard, vehicles, appointments, reviews
│   └── mechanic/     # Mechanic dashboard, pending requests, appointment details
└── util/             # Password hashing
```

## Building

Open the project in Android Studio and run on a device/emulator with API 29+.
