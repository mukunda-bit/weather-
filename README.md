# 🌤️ Real-Time Weather Web Application

A simple and responsive **Real-Time Weather Web Application** built using **Python, Flask, HTML, and CSS**. The application allows users to search for any city and view its current weather conditions along with a **7-day weather forecast**.

The application uses the **Open-Meteo API** to obtain location and weather information.

---

## 📌 Features

- 🔍 Search weather by city name
- 📍 Automatically identifies the searched location
- 🌡️ Displays current temperature
- 🌤️ Shows current weather condition
- 💧 Displays humidity
- 🌡️ Shows "feels like" temperature
- 💨 Displays wind speed
- 🌧️ Displays current precipitation
- 📅 Provides a 7-day weather forecast
- 🌧️ Shows daily precipitation probability
- 📱 Responsive design for desktop and mobile devices
- ❌ Displays meaningful error messages when a city cannot be found or weather data cannot be retrieved

---

## 🛠️ Technologies Used

| Technology               | Purpose                               |
| ------------------------ | ------------------------------------- |
| Python                   | Main programming language             |
| Flask                    | Web application framework             |
| Requests                 | Sending API requests                  |
| HTML                     | Web page structure                    |
| CSS                      | Styling and responsive design         |
| Open-Meteo Geocoding API | Finding city coordinates              |
| Open-Meteo Forecast API  | Retrieving weather data               |
| Jinja2                   | Rendering dynamic weather information |

---

## 🏗️ Project Architecture

The application follows this basic workflow:

```text
User
  │
  ▼
Enter City Name
  │
  ▼
Flask Web Application
  │
  ▼
Open-Meteo Geocoding API
  │
  ▼
Latitude & Longitude
  │
  ▼
Open-Meteo Weather API
  │
  ▼
Current Weather + 7-Day Forecast
  │
  ▼
Flask/Jinja2 Template
  │
  ▼
Weather Information Displayed
```

---

## 📂 Project Structure

```text
weather-app/
│
├── import requests.py
└── README.md
```

The project currently contains the Flask application, including the frontend HTML/CSS, inside the Python file.

---

## ⚙️ How the Application Works

### 1. User enters a city

The user enters a city name into the search box and submits the form.

```text
Enter city name → Search
```

The Flask route receives the city through a `POST` request.

---

### 2. Find the city coordinates

The application sends the city name to the Open-Meteo Geocoding API.

It retrieves information such as:

- City name
- Country
- State/administrative region
- Latitude
- Longitude

The application also gives preference to Indian locations and specifically considers Karnataka/Bengaluru results when multiple results are returned.

---

### 3. Retrieve weather information

After obtaining the latitude and longitude, the application sends them to the Open-Meteo Forecast API.

The API request retrieves current:

- Temperature
- Relative humidity
- Apparent temperature
- Precipitation
- Weather code
- Wind speed

It also retrieves daily:

- Weather code
- Maximum temperature
- Minimum temperature
- Maximum precipitation probability

The application requests a **7-day forecast**.

---

### 4. Convert weather codes

Open-Meteo returns numerical weather codes.

The application converts these codes into readable descriptions and emojis.

For example:

```text
0  → ☀️ Clear sky
1  → 🌤️ Mainly clear
2  → ⛅ Partly cloudy
3  → ☁️ Overcast
61 → 🌦️ Slight rain
65 → 🌧️ Heavy rain
95 → ⛈️ Thunderstorm
```

The project contains mappings for clear weather, clouds, fog, drizzle, rain, snow, showers, and thunderstorms.

---

## 🖥️ User Interface

The application provides:

### Current Weather Card

The current weather section displays:

- Weather icon
- Temperature
- Weather description
- Feels-like temperature
- Humidity
- Wind speed
- Precipitation

These values are presented in a visually styled weather card.

### 7-Day Forecast

The forecast section displays each day's:

- Date
- Weather icon
- Weather condition
- Minimum temperature
- Maximum temperature
- Rain probability



---

## 🚀 Installation

### Step 1: Install Python

Make sure Python 3 is installed on your computer.

Check the installation:

```bash
python --version
```

---

### Step 2: Install Required Libraries

Install Flask and Requests:

```bash
pip install flask requests
```

---

### Step 3: Run the Application

Run the Python file:

```bash
python "import requests.py"
```

The Flask server starts on:

```text
http://127.0.0.1:5000
```

The project is configured to run the Flask development server on `127.0.0.1` at port `5000`.

---

## 🌐 Using the Application

1. Start the Flask server.
2. Open a browser.
3. Go to:

```text
http://127.0.0.1:5000
```

4. Enter a city name.
5. Click **Search**.
6. View the current weather.
7. View the 7-day forecast.

---

## ❌ Error Handling

The application handles several possible errors.

### Empty City

If no city is entered:

```text
Please enter a city name.
```

### City Not Found

If the geocoding service cannot find the requested city:

```text
City not found.
```

### Weather API Failure

If weather information cannot be retrieved:

```text
Failed to fetch weather data.
```

These error conditions are handled directly in the Flask route.

---

## 📡 APIs Used

### Open-Meteo Geocoding API

Used to convert a city name into geographical coordinates.

```text
https://geocoding-api.open-meteo.com/v1/search
```

### Open-Meteo Forecast API

Used to retrieve current and forecast weather information.

```text
https://api.open-meteo.com/v1/forecast
```

## The application accesses both APIs using Python's `requests` library.

## 📱 Responsive Design

The interface includes CSS media queries to adapt the layout to different screen sizes.

On smaller screens:

- Forecast cards are rearranged.
- Weather details change from four columns to fewer columns.
- The search form changes to a vertical layout.

This makes the application usable on desktop and mobile devices.

---

## 🔒 API & Security

This application does not require an API key for the Open-Meteo endpoints used by the project.

The application also uses a request timeout when communicating with the APIs to prevent requests from waiting indefinitely.

---

## 🔮 Future Enhancements

Possible improvements include:

- 📍 Detect weather using the user's location
- 🌙 Add dark/light mode
- 🌡️ Add Celsius/Fahrenheit selection
- 🔎 Add autocomplete for city searches
- 📊 Add weather charts
- 🌅 Display sunrise and sunset times
- 🌧️ Add hourly weather forecasts
- ⭐ Allow users to save favorite cities
- 🗺️ Add an interactive weather map
- 📈 Add historical weather information
- ☔ Add weather alerts

---

## 🎯 Project Objective

The main objective of this project is to create a simple and user-friendly web application that provides **real-time weather information and a 7-day forecast** based on a city selected by the user.

It demonstrates how **Python, Flask, REST APIs, HTML, CSS, and dynamic web rendering** can be combined to build a practical web application.

---

## 👩‍💻 Author

**Weather Application Project**

Built using Python + Flask + Open-Meteo API.

