# API-INTEGRATION-AND-DATA-VISUALIZATION

*COMPANY* : CODTECH IT SOLUTIONS

*NAME* : SHASHANK SHEKHAR

*INTERN ID* : CT06DF2068

*DOMAIN* : PYTHON PROGRAMMING

*DURATION* : 6 WEEKS

*MENTOR* : NEELA SANTOSH

# Weather Dashboard

## Overview

The `weather_dashboard.py` script is a Python-based application designed to fetch and visualize current temperature data for a predefined list of global cities. Leveraging the OpenWeatherMap API, this script provides a quick and efficient way to monitor real-time temperatures, presenting the information in an easy-to-understand bar chart. This project serves as an excellent example of API integration, data retrieval, and data visualization using popular Python libraries. It's particularly useful for anyone needing a swift overview of weather conditions across different geographical locations, or as a foundational project for more complex weather analysis tools. The script is structured to be highly readable and extensible, making it suitable for both educational purposes and practical applications.

## Features

  * **Real-time Data Fetching**: The script connects to the OpenWeatherMap API to retrieve the most current temperature data for each specified city. This ensures that the displayed information is always up-to-date.
  * **Multi-City Support**: It is configured to fetch data for multiple cities, providing a comprehensive global temperature overview at a glance. The current list includes New York, London, Tokyo, Delhi, Sydney, Cape Town, Ramgarh, and Ranchi, but this can be easily customized to any cities of interest.
  * **Temperature in Celsius**: All temperatures are fetched and displayed in Celsius, offering a standardized unit for comparison across all locations.
  * **Error Handling**: The script includes basic error handling to gracefully manage situations where data for a specific city cannot be retrieved, providing informative messages to the user.
  * **Visual Data Representation**: Utilizes `matplotlib` and `seaborn` to generate a visually appealing bar chart, making temperature comparisons intuitive and immediate. The `coolwarm` palette is employed for an effective visual representation of temperature variations.
  * **Dashboard Output**: The generated chart is saved as `weather_dashboard.png`, allowing for easy sharing or integration into reports and presentations. The plot is also displayed dynamically upon execution.

## How it Works

The core functionality of the `weather_dashboard.py` script revolves around making HTTP requests to the OpenWeatherMap API.

1.  **API Key Configuration**: The script requires an OpenWeatherMap API key, which is embedded directly in the `API_KEY` variable. This key authenticates the requests to the weather service.
2.  **City List Definition**: A Python list named `cities` holds the names of the urban centers for which weather data is to be retrieved. This list can be modified by the user to include any desired locations.
3.  **Data Request Loop**: The script iterates through each city in the `cities` list. For each city, it constructs a URL for the OpenWeatherMap `data/2.5/weather` endpoint.
4.  **Parameters**: The request includes parameters such as the city name (`q`), the API key (`appid`), and the desired unit of measurement (`units='metric'` for Celsius).
5.  **Response Handling**: Upon receiving a response from the API, the script checks the HTTP status code. If the status code is 200 (OK), it parses the JSON response to extract the temperature data. If the status code indicates an error, it prints an error message.
6.  **Data Storage**: The extracted city names and their corresponding temperatures are stored in separate lists: `city_names` and `temperatures_celsius`.
7.  **Visualization**: After all data has been successfully fetched, `seaborn` and `matplotlib` are used to create a bar plot. `seaborn.set(style="whitegrid")` enhances the aesthetic appeal of the plot. The x-axis represents the cities, and the y-axis represents the temperatures in Celsius.
8.  **Output**: Finally, the generated plot is saved as `weather_dashboard.png` in the same directory as the script and displayed on the screen.

## Tools and Libraries Used

This project effectively demonstrates the power of combining several robust Python libraries for data interaction and visualization.

  * **`requests`**: This is an elegant and simple HTTP library for Python, essential for making web requests. In this script, it is used to send GET requests to the OpenWeatherMap API and retrieve weather data. Its simplicity and robust features make it the go-to library for handling HTTP communications in Python applications.
  * **`matplotlib.pyplot`**: A comprehensive library for creating static, animated, and interactive visualizations in Python. Here, `pyplot` is used as the foundational plotting library. It provides the core functionalities for creating figures, axes, and plotting various types of graphs, including the bar chart for temperature visualization. It gives fine-grained control over plot elements.
  * **`seaborn`**: Built on top of `matplotlib`, `seaborn` is a statistical data visualization library that provides a high-level interface for drawing attractive and informative statistical graphics. It simplifies the process of creating complex visualizations. In this script, `seaborn.barplot` is utilized to create the bar chart, and `sns.set(style="whitegrid")` is used to apply a professional-looking grid style to the plot, enhancing its readability and aesthetic quality with minimal code.
  * **OpenWeatherMap API**: This is a widely used online service that provides weather data, including current weather, forecasts, and historical data, through its API. The script leverages its free tier to fetch real-time temperature information. Accessing this API requires an `API_KEY`, which users can obtain by registering on the OpenWeatherMap website.

## Applicability

This `weather_dashboard.py` script has a wide range of applications, both as a standalone utility and as a component within larger systems:

  * **Personal Weather Monitoring**: Individuals can use this script to quickly check temperatures in cities important to them, such as family locations, travel destinations, or business hubs.
  * **Educational Tool**: It serves as an excellent practical example for learning about:
      * API integration and consumption in Python.
      * JSON data parsing.
      * Data manipulation and storage in lists.
      * Basic error handling.
      * Data visualization principles using `matplotlib` and `seaborn`.
  * **Foundation for Advanced Weather Apps**: The script can be extended to include more features, such as:
      * Fetching additional weather parameters (humidity, wind speed, pressure).
      * Implementing a graphical user interface (GUI) using libraries like Tkinter or PyQt.
      * Adding forecast data.
      * Storing historical data in a database.
      * Integrating with web frameworks (Flask, Django) to create a web-based weather dashboard.
      * Scheduling the script to run periodically and update the dashboard automatically.
  * **Business Intelligence**: Businesses with operations or interests in multiple global locations could use a modified version of this script to monitor local weather conditions, which might impact logistics, outdoor operations, or simply provide context for global team communications.
  * **Travel Planning**: Travelers can quickly assess the current climate in their intended destinations.
  * **Demonstrative Project**: Ideal for demonstrating proficiency in Python programming, API interaction, and data visualization in portfolios or technical interviews.

## Setup and Installation

To run this script, you will need Python installed on your system along with the required libraries and an OpenWeatherMap API key.

1.  **Clone the Repository (or download the script):**

    ```bash
    git clone https://github.com/narrowminded/API-INTEGRATION-AND-DATA-VISUALIZATION.git
    cd weather-dashboard
    ```

    (Replace `yourusername` and `weather-dashboard` with your actual GitHub details if you fork/create a repository).

2.  **Install Dependencies:**
    It's highly recommended to use a virtual environment to manage project dependencies.

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    pip install requests matplotlib seaborn
    ```

3.  **Obtain OpenWeatherMap API Key:**

      * Go to the [OpenWeatherMap website](https://openweathermap.org/).
      * Sign up for a free account.
      * Once logged in, navigate to the "API keys" tab to find or generate your API key.

4.  **Configure API Key:**

      * Open the `weather_dashboard.py` file.
      * Replace `'YOUR_API_KEY'` with your actual OpenWeatherMap API key:
        ```python
        API_KEY = '581127197832298e7fd3857ed6bbfefb' # Replace this with your actual key
        ```

5.  **Run the Script:**

    ```bash
    python weather_dashboard.py
    ```

After running the script, a bar chart displaying the temperatures will appear, and an image file named `weather_dashboard.png` will be saved in the same directory.

![Image](https://github.com/user-attachments/assets/655a0b73-0a3a-4126-95df-d049577acd56)
