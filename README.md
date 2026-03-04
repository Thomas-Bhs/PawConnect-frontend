# PawConnect Frontend

Mobile application built with React Native (Expo) for PawConnect — enabling citizens to report animals in distress while allowing agents to manage cases efficiently.

The objective was to deliver a complete frontend + backend MVP in 2 weeks.

The mobile app allows:
    
	•	Citizens to report lost or injured animals
	•	Agents to manage and update report status
	•	Users to receive real-time notifications
	•	Location-based interaction through maps and GPS

## Demo

to try the aaplication locally:
1. Install Expo Go on your phone
   https://expo.dev/go
2. Clone the repository
   ```bash
   git clone https://github.com/Thomas-Bhs/PawConnect-frontend
   ```
3. Install depencies
   ```bash
   yarn install
   ```
4. Start the Expo server
   ```bash
   yarn start
   ```

Available scripts :
```bash
yarn android
yarn ios
```

## Backend

The mobile application is connected to a Node.js REST API deployed on Vercel.

All features (authentication, reports, notifications, photo upload) interact with the backend through secured API endpoints.

Backend repository :
https://github.com/Thomas-Bhs/PawConnect-backend

## Features

### Authentication & Session Management
    •	User signup & login
	•	JWT token storage and secured backend requests
	•	Conditional navigation based on authentication state

### Animal Reporting (Citizen Role)
    •	Create a report (animal type, title, description, status)
	•	Capture GPS location via Expo Location
	•	Upload photo using backend signature + Cloudinary
	•	View personal reports

### Agent Management
    •   View assigned reports
	•	Update report status
	•	Track case progression

### Notifications
    •	Retrieve user notifications
	•	Mark a notification as read
	•	Mark all notifications as read

### Maps & Distance Calculation
    •	Display reports on interactive map
	•	Calculate and show distance between user and report
	•	Quick access to report details

## Architecture

```text
frontend/
  api/               # Backend API calls
  components/        # Domain-based UI components
  screens/           # Application screens
  navigation/        # Stacks and tabs
  reducers/          # Redux slices
  hooks/             # Custom business/UI hooks
  helpers/           # Error handling & utilities
  constants/         # Design system (colors, spacing)
  assets/            # Images, icons, fonts
```


## Technical Stack

    •   React Native
	•	Expo
	•	React Navigation (Stack + Tabs)
	•	Redux Toolkit
	•	React Redux
	•	NativeWind (Tailwind CSS)
	•	Expo Location
	•	Expo Camera
	•	React Native Maps

## Backend integration

The frontend consumes a modular Node.js REST API:

Main endpoints used:

	•	POST /auth/signup
	•	POST /auth/login
	•	POST /animals
	•	GET /animals/me
	•	PATCH /animals/:id/photo
	•	GET /notifications
	•	PATCH /notifications/:id/read
	•	PATCH /notifications/read-all
	•	GET /upload/signature

Backend built with:

	•	Node.js
	•	Express
	•	MongoDB
	•	JWT Authentication

## Error Handling Strategy

Network and backend errors are normalized through:

	•	helpers/appError.js
	•	helpers/readJsonSafely.js

This ensures consistent error messaging and improved user experience.


## Author

PawConnect was developed in 2 weeks as part of the La Capsule bootcamp.

The goal was to design and deliver a complete frontend and backend MVP within a strict two-week deadline.

Built by a team of 5 using GitHub and agile practices (feature branching, collaborative development), the project reflects real-world mobile application delivery under time constraints.
