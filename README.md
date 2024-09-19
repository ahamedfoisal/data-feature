
# Weather-Based Exercise Recommendation System

This project leverages two public APIs—**WeatherAPI** and **Wger API**—to provide personalized exercise recommendations based on the current weather conditions. The goal of this feature is to help users decide whether to work out indoors or outdoors, depending on the weather.

## Features
- Fetches real-time weather data for a specific location using the **WeatherAPI**.
- Retrieves exercise routines from the **Wger API** with filtering for English-only descriptions.
- Based on the weather, suggests either indoor or outdoor exercises.
- Removes HTML tags from exercise descriptions to ensure clean and readable output.

## APIs Used
1. **[WeatherAPI](https://www.weatherapi.com/)**:
   - Provides real-time weather conditions, including temperature, precipitation, and more.
   - API is used to determine whether the weather is suitable for outdoor or indoor exercise.

2. **[Wger API](https://wger.de/en/software/api)**:
   - A fitness API that provides a collection of exercises.
   - API is used to suggest relevant exercises based on the weather.

## Prerequisites

1. **API Keys**:
   To use this project, you will need API keys for both the **WeatherAPI** and the **Wger API**. These API keys should **not** be hardcoded into the Colab notebook. Instead, you can provide them at runtime using Google Colab's `userdata` or store them securely using environment variables.

   - **WeatherAPI Key**: 
     - API Key: `9764fc07b2204b4db21161835241909`
   - **Wger Password**:
     - Username: `ahamedfoisal`
     - Password: `9FTgfQDXv!xbydr`

### Secure API Key Handling in Google Colab:

To prevent exposing your API keys, follow these steps:

1. **Storing Keys in Google Colab**:
   - When running the notebook, you will be prompted to enter your API keys.
   - Run the following code to input your keys at runtime securely:
     ```python
     from google.colab import userdata
     
     # Input your API keys
     weather_api_key = input('Enter your WeatherAPI key: ')
     wger_password = input('Enter your Wger API password: ')
     
     # Store them securely in Colab's userdata
     userdata['weather_api'] = weather_api_key
     userdata['wger_password'] = wger_password
     ```

2. **Using API Keys in the Notebook**:
   - In the notebook, you can retrieve the keys securely without hardcoding them:
     ```python
     WEATHER_API_KEY = userdata.get('weather_api')
     WGER_PASSWORD = userdata.get('wger_password')
     ```

3. **Setting API Keys in `.env` File** (Optional):
   If you're running this locally, you can also store your API keys in an environment file `.env` to keep them secure.

   - Create a `.env` file with the following contents:
     ```
     WEATHER_API_KEY=9764fc07b2204b4db21161835241909
     WGER_PASSWORD=9FTgfQDXv!xbydr
     ```

   - Use the `python-dotenv` package to load the keys:
     ```python
     from dotenv import load_dotenv
     import os

     load_dotenv()

     WEATHER_API_KEY = os.getenv('WEATHER_API_KEY')
     WGER_PASSWORD = os.getenv('WGER_PASSWORD')
     ```

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

### 3. Run the Program
   Run the main script and enter your location when prompted to receive weather data and exercise recommendations:
   ```python
   python weather_exercise.py
   ```

   You will be prompted to enter a location (e.g., city name or zip code):
   ```
   Enter your location (city or zip code): 10003
   ```

   The script will display the current weather, and based on that, suggest either indoor or outdoor exercises.

### 4. Error Handling
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



