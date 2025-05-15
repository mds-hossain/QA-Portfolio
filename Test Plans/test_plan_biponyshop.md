# Test Plan for BiponyShop

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

This test plan outlines the testing scope, approach, and schedule for the **BiponyShop** project, an e-commerce platform. It defines the areas of functionality to be tested, including user registration, product browsing, cart management, and checkout. The plan includes test types and tools, testing priorities, and resources required.

### 1.1 Range
#### 1.1.1 Areas to be tested
- **User Registration**: Verifying correct account creation for both customers and business clients.
- **Product Catalog**: Ensuring the product search, display, and filters are working correctly.
- **Cart and Checkout**: Testing the shopping cart, checkout process, and payment gateway integration.
- **Order History Management**: Ensuring users can view past orders and details.

#### 1.1.2 Non-tested Areas
- **Voucher/Coupon System**: No ability to test coupon generation.
- **Payment System**: Full integration testing will occur post-development.

### 1.2 Purpose of the Tests
The primary goal of testing is to ensure that all functionalities of the **BiponyShop** platform work as expected and meet the user's needs. The testing will also aim to identify and fix any defects before releasing the product to the client.

---

## 2. Types of Tests

- **Smoke Tests**: Basic functionality testing at the beginning of each build.
- **Exploratory Session**: Manual testing to explore potential untested paths.
- **Regression Testing**: Testing after bug fixes or new feature additions to ensure no existing functionality is broken.
- **Functional Testing**: Testing core features like registration, shopping cart, checkout, etc.
- **Cross-Browser Testing**: Ensure the site works across different browsers (Chrome, Firefox, Safari, etc.).

---

## 3. Test Results

The results of all test cases will be compiled into a test report. The report will include details on the functionality tested, results, and a list of identified defects.

---

## 4. Resources and Environment

### 4.1 Testing Tools
- **Bug Tracking Tool**: JIRA
- **Test Case Management**: TestRail
- **Automation Tool**: Selenium for regression testing
- **Performance Testing**: Apache JMeter for load testing

### 4.2 Testing Devices and Environment
- **OS**: Windows 10, macOS
- **Browsers**: Chrome, Firefox, Safari, Edge

---

## 5. Schedule of Tests

| Module Name      | Priority | Date       | Time  | Tester        |
|------------------|----------|------------|-------|---------------|
| User Registration | 5        | 05/01/2024 | 3 hrs | Md Shakhawat  |
| Product Catalog  | 4        | 06/01/2024 | 4 hrs | Md Shakhawat  |
| Cart & Checkout  | 5        | 07/01/2024 | 4 hrs | Md Shakhawat  |
| Order History    | 4        | 08/01/2024 | 3 hrs | Md Shakhawat  |

---

## 6. Summary

This document outlines the test plan for **BiponyShop**. The testing includes functional, usability, performance, and regression tests, using a combination of manual and automated testing to ensure high-quality results. The schedule and resources are set to carry out the tests as per the plan.

