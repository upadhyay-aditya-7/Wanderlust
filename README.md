# Wanderlust 🌍

A full-stack property and vacation rental listing web application built with Node.js, Express.js, EJS, and MongoDB. Users can explore, list, search, and review properties around the world with interactive map integration and cloud image storage.

---

## ✨ Features

* **Property Listings (CRUD):** Create, view, edit, and delete property/hotel listings with detailed descriptions, pricing, country, and location metadata.
* **Category & Country Filtering:** Browse and filter properties seamlessly based on destination country and listing categories.
* **Authentication & Authorization:** Secure user registration, login, and session persistence powered by **Passport.js** (`passport-local`) and `connect-mongo`, ensuring only listing/review owners can edit or delete their content.
* **Interactive Reviews & Ratings:** Authenticated users can leave star ratings and written reviews on listings.
* **Cloud Image Storage:** Seamless image upload and optimization handled via **Multer** and **Cloudinary**.
* **Interactive Geocoding Maps:** Integrates Geocoding APIs to convert property addresses into coordinates and display accurate pins on an interactive map.
* **Health-Check Endpoint:** Lightweight `/ping` route configured for uptime monitoring (`UptimeRobot`) to prevent Render free-tier cold starts without generating database session overhead.

---

## 🛠️ Tech Stack

* **Backend:** Node.js, Express.js
* **Frontend & Templating:** EJS, `ejs-mate`, Bootstrap, HTML5, CSS3
* **Database & Sessions:** MongoDB Atlas, Mongoose, `connect-mongo`, `express-session`
* **Authentication:** Passport.js (`passport-local`, `passport-local-mongoose`)
* **Media & Maps:** Cloudinary, Multer, Geocoding API
* **Deployment:** Render

---

## 📁 Project Structure

```text
wanderlust/
├── models/          # Mongoose schemas (Listing, Review, User)
├── routes/          # Express routers (listings, reviews, users)
├── views/           # EJS templates & layouts
├── public/          # Static assets (CSS, client-side JS)
├── utils/           # Custom error handlers & async wrappers
├── app.js           # Main Express application entry point
├── .env             # Environment variables (ignored in Git)
└── package.json     # Project dependencies & scripts
```

---

## 🚀 Getting Started

### Prerequisites

* [Node.js](https://nodejs.org/) (v18+ recommended)
* [MongoDB Atlas](https://www.mongodb.com/atlas) account
* [Cloudinary](https://cloudinary.com/) account
* Geocoding / Map API Token (e.g., Mapbox)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/wanderlust.git
   cd wanderlust
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure environment variables:**
   Create a `.env` file in the root directory and add the following keys:
   ```env
   ATLASDB_URL=your_mongodb_atlas_connection_string
   SECRET=your_session_secret_key
   CLOUD_NAME=your_cloudinary_cloud_name
   CLOUD_API_KEY=your_cloudinary_api_key
   CLOUD_API_SECRET=your_cloudinary_api_secret
   MAP_TOKEN=your_geocoding_map_token
   ```

4. **Run the application locally:**
   ```bash
   node app.js
   ```
   Open [http://localhost:8080/listings](http://localhost:8080/listings) in your browser.

---

## 🩺 Health Check

To keep the Render deployment responsive, a lightweight endpoint is exposed before session middleware:

* `GET /ping` — Returns `200 OK` (`pong`) without writing session records to MongoDB.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).