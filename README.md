




# Weather-Based Exercise Recommendation System

This project leverages two public APIs—**WeatherAPI** and **Wger API**—to provide personalized exercise recommendations based on the current weather conditions. The goal of this feature is to help users decide whether to work out indoors or outdoors, depending on the weather.

## Features
- Fetches real-time weather data for a specific location using the **WeatherAPI**.
- Retrieves exercise routines from the **Wger API** with filtering for English-only descriptions.
- Based on the weather, suggests either indoor or outdoor exercises.
- Removes HTML tags from exercise descriptions to ensure clean and readable output.

## APIs Used
1. **[WeatherAPI](https://www.weatherapi.com/)**
   - Provides real-time weather conditions, including temperature, precipitation, and more.
   - API is used to determine whether the weather is suitable for outdoor or indoor exercise.

2. **[Wger API](https://wger.de/en/software/api)**
   - A fitness API that provides a collection of exercises.
   - API is used to suggest relevant exercises based on the weather.

## Prerequisites

1. **API Keys**:
   - **WeatherAPI**: You will need an API key from [WeatherAPI](https://www.weatherapi.com/signup.aspx). Once you have the key, store it in your `userdata`.
   - **Wger API**: If you want to access private endpoints (like personal workout plans), you’ll need your Wger account credentials. Otherwise, public endpoints (like exercises) are accessible without authentication.

2. **Google Colab or Local Environment**:
   - This project was developed using **Google Colab**. However, you can run it locally in any Python environment as long as you install the necessary dependencies.

## Setup and Running the Project

### 1. Clone the Repository
   Clone this repository to your local environment or open it in Google Colab:
   ```bash
   git clone https://github.com/ahamedfoisal/data-feature.git
   cd data-feature
   ```

### 2. Install Required Libraries
   If running locally, you will need to install the `requests` library:
   ```bash
   pip install requests
   ```

### 3. Set Up API Keys
   Store your **WeatherAPI** and **Wger API** keys in the `userdata` object in Google Colab or locally in a `.env` file:
   ```python
   from google.colab import userdata
   userdata = {
       'weather_api': 'YOUR_WEATHER_API_KEY',
       'wger_password': 'YOUR_WGER_PASSWORD'
   }
   ```

### 4. Running the Program
   Run the main script and enter your location when prompted to receive weather data and exercise recommendations:
   ```python
   python weather_exercise.py
   ```

   You will be prompted to enter a location (e.g., city name or zip code):
   ```
   Enter your location (city or zip code): 10003
   ```

   The script will display the current weather, and based on that, suggest either indoor or outdoor exercises.

### 5. Error Handling
   The code handles common issues like:
   - Invalid API keys.
   - Location not found.
   - Issues with data fetching from the APIs.

## Example Output

```
Enter your location (city or zip code): 10003
Current weather: Partly cloudy, Temperature: 15.3°C
Weather is not favorable, recommending indoor exercises.
Here are some recommended exercises in English:
Exercise Name: Dumbbell Bench Press
Description: Lie on a bench with a dumbbell in each hand and press the weights upwards while keeping your back straight.

Exercise Name: Squats
Description: Stand with your feet shoulder-width apart, then lower your body as if you're sitting in a chair. Push back up through your heels.
```



---

By following the steps and providing your API keys, you can get weather-based exercise recommendations based on real-time weather data.

```

