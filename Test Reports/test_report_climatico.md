# Test Report for Climatico

## Created by: Md Shakhawat Hossain

---

## Contents

1. [Introduction](#introduction)
2. [Test Results](#test-results)
3. [Metrics](#metrics)
4. [Defects Found](#defects-found)
5. [Environment](#environment)
6. [Summary](#summary)

---

## 1. Introduction

This report summarizes the results of the testing activities conducted on the **Climatico** weather app. Testing was focused on verifying the functionality of weather data retrieval, UI display, and cross-browser compatibility.

---

## 2. Test Results

| Module Name     | Status    | Defects Found |
|-----------------|-----------|---------------|
| Weather Data API | Failed    | 1             |
| UI Elements      | Passed    | 0             |
| Cross-Browser    | Passed    | 0             |

---

## 3. Metrics
- **Total Test Cases**: 10
- **Executed Test Cases**: 10
- **Passed**: 9
- **Failed**: 1

---

## 4. Defects Found

| Bug ID  | Severity | Status   | Description                                |
|---------|----------|----------|--------------------------------------------|
| BUG-01  | High     | Open     | Weather data not updating after API call   |

---

## 5. Environment
- **OS**: Windows 10
- **Browsers**: Chrome (v91), Firefox (v89)

---

## 6. Summary

The **Climatico** weather app passed most tests, but the integration with the weather API has issues that need to be resolved. It is recommended that the API update issue be fixed before the app is released.

---

