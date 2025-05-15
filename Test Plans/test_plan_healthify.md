# Test Plan for Healthify

## Version History
| Date       | Version | Changelog                           |
|------------|---------|-------------------------------------|
| 01/03/2024 | 1.0     | Initial document creation           |
| 02/03/2024 | 1.1     | Updates to include test schedule    |

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

This test plan outlines the testing scope, approach, and schedule for the **Healthify** project, a fitness tracker web app. The testing will focus on key functionalities such as user registration, activity tracking, synchronization across devices, and notifications.

### 1.1 Range
#### 1.1.1 Areas to be tested
- **User Registration**: Ensure users can register and log in successfully.
- **Profile Management**: Verify users can manage and edit their profile information.
- **Activity Tracking**: Confirm users can log and track their activities accurately.
- **Data Synchronization**: Ensure the app syncs data correctly between the web and mobile platforms.
- **Notifications**: Check that users receive appropriate notifications based on fitness milestones.

#### 1.1.2 Non-tested Areas
- **Third-Party Integrations**: No testing will be done for third-party apps like Google Fit or Apple Health for now.

### 1.2 Purpose of the Tests
The goal of the tests is to ensure that all key features function as expected, with a focus on usability, data integrity, and cross-device synchronization.

---

## 2. Types of Tests

- **Smoke Testing**: Verify the basic functionality of user registration, login, and profile management.
- **Exploratory Testing**: Manually explore the app to identify any untested areas and verify user experience.
- **Regression Testing**: Ensure that newly implemented features do not interfere with existing functionalities.
- **Functional Testing**: Validate core features like registration, activity tracking, and synchronization.
- **Cross-Device Testing**: Ensure the app functions across different operating systems (macOS, Windows, iOS, Android).
- **Performance Testing**: Verify that the app can handle multiple users logging activities at the same time.

---

## 3. Test Results

The test results will be compiled into a detailed report that documents the status of each feature tested and any defects identified.

---

## 4. Resources & Environment

### 4.1 Testing Tools
- **Bug Tracking Tool**: JIRA
- **Test Case Management**: TestRail
- **API Testing**: Postman
- **Automation Tool**: Selenium WebDriver for regression testing

### 4.2 Testing Devices & Environment
- **OS**: Windows 10, macOS
- **Browsers**: Chrome, Firefox, Safari
- **Mobile Devices**: iOS, Android (for cross-device testing)

---

## 5. Schedule of Tests

| Module Name            | Priority | Date       | Time  | Tester        |
|------------------------|----------|------------|-------|---------------|
| User Registration      | 5        | 01/03/2024 | 3 hrs | Md Shakhawat  |
| Profile Management     | 4        | 02/03/2024 | 3 hrs | Md Shakhawat  |
| Activity Tracking      | 5        | 03/03/2024 | 4 hrs | Md Shakhawat  |
| Data Synchronization   | 5        | 04/03/2024 | 3 hrs | Md Shakhawat  |
| Notifications          | 3        | 05/03/2024 | 2 hrs | Md Shakhawat  |

---

## 6. Summary

This test plan details the scope and approach for testing **Healthify**. Key areas such as registration, profile management, activity tracking, and synchronization are prioritized, with a focus on delivering a seamless user experience across devices.

---

