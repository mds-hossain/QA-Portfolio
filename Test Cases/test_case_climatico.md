# Test Case for Weather Data API

## Test Case ID: TC-01
### Summary: Verifying API integration to fetch weather data
- **Description**: Testing the integration with OpenWeather API for correct weather data.
- **Preconditions**: The app must be able to access the internet and fetch data from OpenWeather API.

### Steps
| Step | Action                                     | Expected Result                        | Status |
|------|--------------------------------------------|----------------------------------------|--------|
| 1    | Enter a city name in the search bar        | The search field is populated with the city name | Pass   |
| 2    | Click the "Get Weather" button             | The app should call the API and display weather data for that city | Pass   |
| 3    | Verify the displayed temperature and humidity | Temperature and humidity should match the API response | Pass   |

### Expected Result
- The weather data, including temperature and humidity, is fetched from the API and displayed on the UI.

### Actual Result
- The weather data is correctly fetched and displayed.

---

# Test Case for UI Elements

## Test Case ID: TC-02
### Summary: Verifying UI components are responsive and correctly display weather data
- **Description**: Ensure the UI components, such as temperature, city name, and weather description, display correctly.
- **Preconditions**: The app is loaded, and the weather data is successfully retrieved.

### Steps
| Step | Action                                     | Expected Result                        | Status |
|------|--------------------------------------------|----------------------------------------|--------|
| 1    | Load the app with weather data for a city  | UI elements display correctly (e.g., temperature, city name) | Pass   |
| 2    | Resize the browser window                  | The UI should be responsive and adjust to the window size | Pass   |
| 3    | Verify that the weather icons change based on conditions | Correct weather icons are displayed | Pass   |

### Expected Result
- The UI adjusts properly, and all weather data is displayed as expected.

### Actual Result
- The UI is responsive, and weather data displays correctly across different screen sizes.

