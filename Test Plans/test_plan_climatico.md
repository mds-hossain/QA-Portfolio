# Test Plan for Climatico

## Version History
| Date       | Version | Changelog                           |
|------------|---------|-------------------------------------|
| 01/01/2024 | 1.0     | Initial document creation           |
| 02/01/2024 | 1.1     | Updates to include test schedule    |

## Created by: Md Shakhawat Hossain

---

## Contents

1. [Introduction](#introduction)
2. [Scope](#scope)
3. [Types of Tests](#types-of-tests)
4. [Test Results](#test-results)
5. [Resources & Environment](#resources-environment)
6. [Schedule of Tests](#schedule-of-tests)
7. [Summary](#summary)

---

## 1. Introduction

This test plan outlines the testing scope, approach, and schedule for the **Climatico** project, a weather application. The plan defines the areas of functionality to be tested, including user input, API integration for weather data, and UI functionality.

### 1.1 Range
#### 1.1.1 Areas to be tested
- **Weather Data API**: Testing the OpenWeather API for correct data retrieval.
- **UI Elements**: Ensuring that temperature, humidity, and other weather information display correctly.
- **Cross-Browser Testing**: Verifying the app works correctly in Chrome, Firefox, and Safari.

#### 1.1.2 Non-tested Areas
- **Payment System**: Not applicable as no payment features are included.

### 1.2 Purpose of the Tests
The goal of testing is to ensure the weather data is displayed correctly, UI elements are responsive, and the API integration works as expected.

---

## 2. Types of Tests

- **Smoke Testing**: Quick checks on the basic functionality (e.g., retrieving weather data).
- **Exploratory Testing**: Manually exploring the application to identify bugs or missed features.
- **Functional Testing**: Checking core features like weather data retrieval and display.
- **Cross-Browser Testing**: Ensuring compatibility across major browsers.

---

## 3. Test Results

The test results will be summarized in a report. The report will include the status of each tested feature and any defects found.

---

## 4. Resources and Environment

### 4.1 Testing Tools
- **Bug Tracking Tool**: JIRA
- **Testing Framework**: Selenium for automated UI testing
- **API Testing Tool**: Postman

### 4.2 Testing Devices & Environment
- **OS**: macOS, Windows 10
- **Browsers**: Chrome, Firefox, Safari

---

## 5. Schedule of Tests

| Module Name      | Priority | Date       | Time  | Tester        |
|------------------|----------|------------|-------|---------------|
| Weather API      | 5        | 10/01/2024 | 3 hrs | Md Shakhawat  |
| UI Testing       | 4        | 11/01/2024 | 2 hrs | Md Shakhawat  |
| Cross-Browser    | 5        | 12/01/2024 | 3 hrs | Md Shakhawat  |

---

## 6. Summary

This test plan provides a structured approach to testing the **Climatico** weather app. It outlines the areas to be tested, the test types, and the resources needed to perform comprehensive testing.

