# Test Plan for Taskyfier

## Version History
| Date       | Version | Changelog                           |
|------------|---------|-------------------------------------|
| 01/04/2024 | 1.0     | Initial document creation           |
| 02/04/2024 | 1.1     | Updates to include test schedule    |

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

This test plan outlines the testing scope, approach, and schedule for the **Taskyfier** project, a task management web app. The testing will focus on core functionalities like task creation, editing, deletion, notifications, and synchronization across devices.

### 1.1 Range
#### 1.1.1 Areas to be tested
- **Task Creation**: Ensure users can add tasks.
- **Task Editing**: Verify users can edit existing tasks.
- **Task Deletion**: Ensure users can delete tasks.
- **Task Notifications**: Test if users get notifications based on deadlines or task updates.
- **Data Synchronization**: Ensure tasks sync across devices.

#### 1.1.2 Non-tested Areas
- **Third-Party Integrations**: No testing will be done for third-party integrations like Google Calendar for now.

### 1.2 Purpose of the Tests
The goal of these tests is to ensure that all key features work as intended, with a focus on usability, data synchronization, and overall app performance.

---

## 2. Types of Tests

- **Smoke Testing**: Verify basic functionality of task creation, editing, and deletion.
- **Exploratory Testing**: Manually explore the app to identify untested areas and ensure a smooth user experience.
- **Regression Testing**: Ensure new features or fixes do not break existing functionalities.
- **Functional Testing**: Validate core task-related features like creation, editing, and notifications.
- **Cross-Device Testing**: Ensure compatibility across multiple platforms (desktop and mobile).
- **Performance Testing**: Test app responsiveness under heavy usage with a large number of tasks.

---

## 3. Test Results

The test results will be compiled into a detailed report that documents the status of each feature tested and any defects found.

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
- **Mobile Devices**: iOS, Android

---

## 5. Schedule of Tests

| Module Name            | Priority | Date       | Time  | Tester        |
|------------------------|----------|------------|-------|---------------|
| Task Creation          | 5        | 05/04/2024 | 3 hrs | Md Shakhawat  |
| Task Editing           | 5        | 06/04/2024 | 3 hrs | Md Shakhawat  |
| Task Deletion          | 5        | 07/04/2024 | 2 hrs | Md Shakhawat  |
| Task Notifications     | 5        | 08/04/2024 | 3 hrs | Md Shakhawat  |
| Data Synchronization   | 5        | 09/04/2024 | 3 hrs | Md Shakhawat  |

---

## 6. Summary

This test plan outlines the scope and approach for testing the **Taskyfier** application. Focus will be placed on ensuring that task management features work correctly, data syncs across devices, and performance remains stable under load.

---

