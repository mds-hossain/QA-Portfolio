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
