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

---

### **3. Bug Report for Climatico (Weather App)**

```markdown
# Bug Report for Climatico

## Bug ID: BUG-01
- **Test Case ID**: TC-01
- **Author**: Md Shakhawat Hossain
- **OS**: Windows 10
- **Browser**: Chrome
- **Date**: 10/01/2024
- **Priority**: High
- **Severity**: Critical

---

## Title
Weather data not updating after API call

---

## Description
After making a request to the API to fetch weather data, the data does not update on the UI. The user interface remains static with the previous weather data.

---

## Preconditions
- User has entered a valid city name.
- The app is connected to the internet.

---

## Steps to Reproduce
| Step | Action                                     | Expected Result                          | Actual Result                |
|------|--------------------------------------------|------------------------------------------|------------------------------|
| 1    | Enter city name "Berlin"                   | The city name should appear in the search field | Pass                         |
| 2    | Click "Get Weather"                        | The app should fetch and display data for Berlin | No data update shown         |
| 3    | Refresh the page                           | The weather data should be updated       | No change                    |

---

## Expected Result
- Weather data should update on the UI after the API call.

---

## Actual Result
- Weather data remains static; no update is shown.

---

## Screenshots
- [Bug Screenshot](https://link-to-screenshot)

---

## Resolution
- **Status**: Open
