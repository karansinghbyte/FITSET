# ProFit Connect — Fitness Assistant

ProFit Connect is a fitness platform with a modern landing page and a fitness tracking application. Users can explore workout programs, create an account, receive personalized recommendations, and track their activity and progress.

## Table of Contents

- [Project Overview](#project-overview)
- [Project Structure](#project-structure)
- [Features](#features)
- [User Flow](#user-flow)
- [Getting Started](#getting-started)
- [Backend and Database Setup](#backend-and-database-setup)
- [Testing the Application](#testing-the-application)
- [Troubleshooting MongoDB Atlas](#troubleshooting-mongodb-atlas)
- [Next Steps](#next-steps)
- [Support](#support)

## Project Overview

The project has two main frontend experiences:

1. **Landing page (`index.html`)** — introduces the platform, showcases its features, and directs visitors to authentication.
2. **Authentication and dashboard (`auth.html`)** — supports registration and login, then provides fitness tracking and personalized recommendations.

The backend uses **Spring Boot**, with **MongoDB Atlas** as the database and **Gemini API** integration for AI-powered features.

## Project Structure

```text
frontend/
├── index.html          # Main landing page
├── auth.html           # Authentication and fitness dashboard
├── landing.html        # Backup landing page
├── style.css           # Landing page styles
├── landing.css         # Backup landing page styles
├── css/
│   └── style.css       # Authentication and dashboard styles
└── js/
    ├── app.js          # API client, authentication, and dashboard logic
    └── landing.js      # Landing page interactions
```

### Key Files

| File | Purpose |
|---|---|
| `index.html` | Landing page with hero section, features, workouts, trainers, pricing, and footer |
| `auth.html` | Registration, login, and fitness dashboard interface |
| `style.css` | Responsive styling and animations for the landing page |
| `css/style.css` | Styling for authentication forms and dashboard components |
| `js/landing.js` | Workout filtering, smooth scrolling, and scroll animations |
| `js/app.js` | API communication, authentication, dashboard functionality, and tracking |

## Features

### Landing Page

- Hero section with calls to action
- Feature showcase
- Filterable workout programs
- Trainer profiles: Shivam, Bhoomika, Shilpa, and Akriti
- Progress-tracking preview
- Basic, Pro, and Elite pricing plans
- Contact footer
- Smooth animations
- Responsive mobile layout

### Authentication and Dashboard

- User registration with a fitness profile
- User login
- BMI calculation
- AI-powered workout recommendations using the Gemini API
- AI-powered nutrition plans
- Daily activity tracking
- Progress analytics
- Profile management

> **Note:** The backend must be running and correctly configured for features that depend on server APIs or database access.

## User Flow

1. The user opens `index.html`.
2. The user selects **Start Free Trial** or another getting-started call to action.
3. The browser redirects to `auth.html`.
4. The user registers or logs in.
5. The user opens the personalized dashboard.
6. The application requests AI-generated recommendations through the backend and Gemini API.
7. The user records daily activities and monitors progress over time.

## Getting Started

### Prerequisites

- A web browser
- A code editor such as Visual Studio Code
- The project's Spring Boot backend
- A MongoDB Atlas cluster and valid credentials
- A Gemini API key if AI-powered features require one
- A local development server, such as the VS Code Live Server extension

### 1. Start the MongoDB Database

Make sure the MongoDB Atlas cluster is available and that the backend connection settings are correct. See [Troubleshooting MongoDB Atlas](#troubleshooting-mongodb-atlas).

### 2. Configure the Backend

Open the backend configuration file:

```text
backend/src/main/resources/application.properties
```

Verify that the MongoDB connection URI and any required API settings are configured. Keep passwords and API keys private; do not commit real secrets to version control.

### 3. Start the Spring Boot Backend

Run the Spring Boot application using your preferred IDE or the project's supported command. The main application class is:

```text
FitSetApplication.java
```

The expected local backend URL is:

```text
http://localhost:8080
```

Confirm the actual port in the backend configuration if it differs.

### 4. Start the Frontend

Open the `frontend` folder in Visual Studio Code and launch `index.html` using Live Server, or use another local web server.

For the best experience, start from `index.html` rather than opening the dashboard directly.

## Backend and Database Setup

The application flow depends on these components:

- **Frontend:** HTML, CSS, and JavaScript
- **Backend:** Spring Boot
- **Database:** MongoDB Atlas
- **AI integration:** Gemini API

Make sure the frontend API base URL matches the address and port where the backend is running. Also verify that the backend's database URI and AI API configuration are set correctly.

## Testing the Application

Use this checklist to verify the main functionality:

- [ ] Open the landing page and check that it displays correctly.
- [ ] Test the navigation and landing-page animations.
- [ ] Click a call to action and confirm it opens `auth.html`.
- [ ] Register a test account.
- [ ] Confirm that registration data is stored in MongoDB.
- [ ] Log in using the test account.
- [ ] Open the dashboard and check the fitness profile.
- [ ] Test BMI calculation and daily activity tracking.
- [ ] Generate workout recommendations.
- [ ] Generate a nutrition plan.
- [ ] Confirm that progress analytics update as expected.

## Troubleshooting MongoDB Atlas

If the backend times out while connecting to MongoDB Atlas, work through the following checks.

### 1. Check Network Access

1. Open the [MongoDB Atlas dashboard](https://cloud.mongodb.com/).
2. Navigate to **Network Access**.
3. Add your current public IP address to the access list.
4. Save the change and allow time for it to take effect.

For temporary testing only, Atlas supports allowing access from `0.0.0.0/0`. This permits connections from any IP address and is **not recommended for production**. Use the narrowest possible IP access rule.

### 2. Verify the Connection String

Open:

```text
backend/src/main/resources/application.properties
```

Check that the MongoDB URI contains the correct:

- Database username
- Database password
- Cluster hostname
- Database name

If the password contains special characters, ensure they are URL-encoded as required by the connection-string format. Never share a connection string containing credentials publicly.

### 3. Test the Connection

If `mongosh` is installed, test connectivity with your own cluster hostname and username:

```bash
mongosh "mongodb+srv://<your-cluster-host>/<database-name>" --username <your-username>
```

Enter the password when prompted. Replace the placeholders with your actual values; do not paste credentials into public logs or shared screenshots.

### 4. Check Network Restrictions

- Confirm that your current network allows outbound connections to MongoDB Atlas.
- Check whether a VPN, antivirus, or firewall is interfering with the connection.
- If possible, test using another trusted network.
- Review the backend logs for the full connection error.

Avoid disabling your firewall as a routine fix. Prefer identifying and correcting the specific network rule that blocks the connection.

## Next Steps

1. **Resolve the MongoDB connection** by checking Atlas network access and the connection URI.
2. **Start the Spring Boot backend** and confirm that it is reachable at the configured local URL.
3. **Test registration and login** with a test account.
4. **Verify database persistence** by confirming that test data is saved to MongoDB.
5. **Test the AI features** and check the Gemini API configuration and backend logs.
6. **Run the full application checklist** before sharing the project with others.

## Support

- **Email:** `ks612353@gmail.com`
- **Phone:** `8423483661`
- **Availability:** India

---

*Built with ❤️ by the ProFit Connect Team.*

**Transform your life, one workout at a time! 💪**
