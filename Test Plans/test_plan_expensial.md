# Test Plan for Expensial

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

This test plan outlines the testing scope, approach, and schedule for the **Expensial** project, an expense tracker. The plan will test the core features like adding, editing, and deleting expenses, generating reports, and ensuring secure user management. The plan also includes test types, tools, and testing priorities.

### 1.1 Range
#### 1.1.1 Areas to be tested
- **Expense Tracking**: Ensuring users can add, edit, and delete expenses.
- **Income Management**: Verifying income tracking functionalities.
- **Dashboard**: Testing the dashboard that displays expenses vs income and overall financial summary.
- **Data Export**: Ensuring users can export data to CSV.

#### 1.1.2 Non-tested Areas
- **Mobile Compatibility**: No testing for mobile app version (if any) for now.
  
### 1.2 Purpose of the Tests
To verify the functionality of the expense tracker application and ensure data consistency, security, and user-friendly experience across different browsers.

---

## 2. Types of Tests

- **Smoke Testing**: Check the basic functionality of adding, editing, and deleting expenses.
- **Exploratory Testing**: Manually test to discover untested areas and verify the user experience.
- **Regression Testing**: Ensure that new features or bug fixes do not affect existing functionality.
- **Functional Testing**: Focus on verifying the core functionalities, such as adding expenses, generating reports, and securing user data.
- **Cross-Browser Testing**: Ensure the application functions properly in multiple browsers.

---

## 3. Test Results

The results will be compiled into a test report that will include the status of each tested feature, with identified defects documented.

---

## 4. Resources & Environment

### 4.1 Testing Tools
- **Bug Tracking Tool**: JIRA
- **Test Case Management**: TestRail
- **API Testing**: Postman for testing APIs used in data retrieval.
- **Automation Tool**: Selenium WebDriver for regression testing

### 4.2 Testing Devices & Environment
- **OS**: macOS, Windows 10
- **Browsers**: Chrome, Firefox, Safari

---

## 5. Schedule of Tests

| Module Name     | Priority | Date       | Time  | Tester        |
|-----------------|----------|------------|-------|---------------|
| Expense Tracking | 5        | 10/01/2024 | 3 hrs | Md Shakhawat  |
| Income Management| 4        | 11/01/2024 | 2 hrs | Md Shakhawat  |
| Dashboard        | 5        | 12/01/2024 | 3 hrs | Md Shakhawat  |
| Data Export      | 4        | 13/01/2024 | 2 hrs | Md Shakhawat  |

---

## 6. Summary

This test plan outlines the scope, approach, and schedule for testing **Expensial**. The application will undergo comprehensive functional, exploratory, and cross-browser testing to ensure its reliability and performance. Testing will also focus on data consistency and usability.

