# ResQNow
Site Live at : https://resqnow.netlify.app

# ResqNow: The Emergency Ambulance Booking System 🚑

![ResqNow Banner](https://your-image-url-here.com/resqnow_banner.png) **A web-based platform for fast and reliable ambulance booking during critical emergencies. ResqNow bridges the gap between patients in need and ambulance services, ensuring timely medical attention during the crucial "golden hour."**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Deployment](https://img.shields.io/badge/Deployment-Live-brightgreen)](https://resqnow.your-live-url.com) [![Build Status](https://img.shields.io/badge/Build-Passing-success)](https://github.com/your-username/resqnow) ---

## 📍 Table of Contents

- [About The Project](#about-the-project)
- [Live Demo](#live-demo)
- [Screenshots](#screenshots)
- [Key Features](#key-features)
- [Technology Stack](#technology-stack)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Local Installation Guide](#local-installation-guide)
- [How It Works (User Flow)](#how-it-works-user-flow)
- [API Endpoints](#api-endpoints)
- [Project Roadmap](#project-roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## 📖 About The Project

In many regions, including here in India, emergency medical response times can be unpredictable. The process of finding, calling, and dispatching a nearby ambulance is often manual, chaotic, and stressful. This delay can have life-threatening consequences.

**ResqNow** was built to solve this problem. It is a real-time, map-based platform that:
* **Connects** users directly with the nearest available ambulance services.
* **Streamlines** the booking process into a few simple clicks.
* **Provides** live tracking and transparent communication, reducing anxiety for patients and their families.

Our mission is to leverage technology to save lives by making emergency medical transport accessible, reliable, and efficient for everyone.

---

## 🚀 Live Demo

You can view the live, deployed version of the project here:

**[https://resqnow.your-live-url.com](https://resqnow.your-live-url.com)** ---

## 📸 Screenshots

<table>
  <tr>
    <td><img src="https://your-image-url-here.com/homepage.png" alt="Homepage Screenshot" width="400"/></td>
    <td><img src="https://your-image-url-here.com/booking_form.png" alt="Booking Form Screenshot" width="400"/></td>
  </tr>
  <tr>
    <td align="center"><sub><b>Homepage</b></sub></td>
    <td align="center"><sub><b>Booking Form</b></sub></td>
  </tr>
  <tr>
    <td><img src="https://your-image-url-here.com/live_tracking.png" alt="Live Tracking Screenshot" width="400"/></td>
    <td><img src="https://your-image-url-here.com/user_dashboard.png" alt="User Dashboard Screenshot" width="400"/></td>
  </tr>
  <tr>
    <td align="center"><sub><b>Live Ambulance Tracking</b></sub></td>
    <td align="center"><sub><b>User Booking History</b></sub></td>
  </tr>
</table>

---

## ✨ Key Features

### For Patients / Users:
* **One-Click Booking:** Intuitive interface to book an ambulance in seconds.
* **Real-Time Tracking:** Live map view to track the ambulance's location and ETA.
* **Multiple Ambulance Types:** Choose between Basic Life Support (BLS), Advanced Life Support (ALS), and Patient Transport vehicles.
* **Transparent Pricing:** Get an estimated fare before confirming the booking.
* **User Profiles:** Manage personal details and view complete booking history.
* **SMS/Notification Alerts:** Receive timely updates on your booking status.

### For Ambulance Drivers / Providers:
* **Driver Dashboard:** A dedicated interface to accept or reject incoming ride requests.
* **Optimized Routing:** View the patient's location and the best route to reach them.
* **Status Updates:** Easily update status from "En Route" to "Arrived" to "At Hospital."
* **Earnings Tracker:** Monitor daily and monthly earnings.

### For Administrators:
* **Centralized Dashboard:** Overview of all ongoing rides, available drivers, and user activity.
* **Fleet Management:** Add, edit, or remove vehicles and drivers from the system.
* **Analytics & Reporting:** View data on peak hours, popular locations, and overall system performance.

---

## 🛠️ Technology Stack

This project is built with modern web technologies to ensure performance, scalability, and a great user experience.

* **Frontend:** React, Vite, React Router, Axios, Mapbox GL JS / Leaflet
* **Backend:** Node.js, Express.js
* **Database:** MongoDB with Mongoose
* **Authentication:** JSON Web Tokens (JWT)
* **Real-Time Communication:** WebSockets (Socket.io)
* **Deployment:**
    * Frontend on **Netlify**
    * Backend on **Render**

---

## 🏁 Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

Make sure you have the following software installed on your machine:
* Node.js (v18.x or later)
* npm (v9.x or later) or yarn
* Git
* A MongoDB account (you can get a free cluster from [MongoDB Atlas](https://www.mongodb.com/cloud/atlas))

### Local Installation Guide

1.  **Clone the repository:**
    ```sh
    git clone [https://github.com/your-username/resqnow.git](https://github.com/your-username/resqnow.git)
    cd resqnow
    ```

2.  **Set up the Backend Server:**
    ```sh
    cd server
    npm install
    ```
    Create a `.env` file in the `server` directory and add the following variables:
    ```env
    MONGO_URI=your_mongodb_connection_string
    JWT_SECRET=your_super_secret_jwt_key
    PORT=10000
    ```

3.  **Set up the Frontend Client:**
    ```sh
    cd ../client
    npm install
    ```
    Create a `.env` file in the `client` directory and add the backend API URL:
    ```env
    VITE_API_BASE_URL=http://localhost:10000
    ```

4.  **Run the application:**
    * To start the backend server, run this from the `/server` directory:
        ```sh
        npm run dev
        ```
    * To start the frontend client, run this from the `/client` directory in a separate terminal:
        ```sh
        npm run dev
        ```

The application should now be running locally at `http://localhost:5173`.

---

## ⚙️ How It Works (User Flow)

1.  **Sign Up / Login:** A user creates an account or logs in.
2.  **Enter Details:** The user enters their current location (or allows GPS access) and their destination (e.g., a hospital).
3.  **Select Ambulance:** They choose the type of ambulance needed (BLS, ALS, etc.).
4.  **Confirm Booking:** The system calculates an estimated fare and time. The user confirms the booking.
5.  **Driver Allocation:** A request is sent to all nearby, available drivers.
6.  **Driver Acceptance:** The first driver to accept is assigned the ride.
7.  **Live Tracking:** The user receives a confirmation and can now track the ambulance's location in real-time on the map.
8.  **Ride Completion:** The driver updates the status upon reaching the patient and then the hospital. The trip is logged in the user's and driver's history.

---

## 🌐 API Endpoints

The backend exposes a RESTful API for all operations. Here are some of the key endpoints:

| Method | Endpoint                    | Description                                |
| :----- | :-------------------------- | :----------------------------------------- |
| `POST` | `/api/auth/register`        | Register a new user.                       |
| `POST` | `/api/auth/login`           | Log in a user and receive a JWT.           |
| `POST` | `/api/bookings`             | Create a new ambulance booking.            |
| `GET`  | `/api/bookings/user/:userId`  | Get all bookings for a specific user.      |
| `GET`  | `/api/drivers/available`    | Get a list of all available drivers.       |
| `PUT`  | `/api/bookings/:bookingId`  | Update the status of a booking.            |

---

## 🗺️ Project Roadmap

While the core functionality is complete, there are many exciting features planned for the future:

* [ ] **Payment Gateway Integration:** Allow users to pay for services directly through the app using Stripe or Razorpay.
* [ ] **In-App Chat:** Enable direct, real-time communication between the user and the driver.
* [ ] **Multi-language Support:** Add support for Hindi and other regional languages.
* [ ] **Rate & Review System:** Allow users to rate their experience with the driver and service.
* [ ] **Dedicated Mobile App:** Develop native Android and iOS applications for a better mobile experience.

---

## 🤝 Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1.  **Fork** the Project
2.  Create your **Feature Branch** (`git checkout -b feature/AmazingFeature`)
3.  **Commit** your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  **Push** to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a **Pull Request**

Please make sure your code adheres to the project's coding standards.

---

## 📜 License

This project is distributed under the MIT License. See `LICENSE.txt` for more information.

---

## 📞 Contact

Your Name - [Your LinkedIn/Twitter Link] - your.email@example.com

Project Link: [https://github.com/your-username/resqnow](https://github.com/your-username/resqnow) ---
