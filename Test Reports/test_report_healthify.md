# Test Report for Healthify

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

This report summarizes the results of the testing activities conducted on **Healthify**, a fitness tracker application. Testing focused on core features, such as registration, profile management, activity tracking, and synchronization across devices.

---

## 2. Test Results

| Module Name            | Status   | Defects Found |
|------------------------|----------|---------------|
| User Registration      | Passed   | 0             |
| Profile Management     | Passed   | 0             |
| Activity Tracking      | Passed   | 0             |
| Data Synchronization   | Failed   | 1             |
| Notifications          | Passed   | 0             |
| App Responsiveness     | Passed   | 0             |

---

## 3. Metrics

- **Total Test Cases**: 7
- **Executed Test Cases**: 7
- **Passed**: 6
- **Failed**: 1
- **Defects Found**: 7

---

## 4. Defects Found

| Bug ID  | Severity | Status   | Description                          |
|---------|----------|----------|--------------------------------------|
| BUG-01  | High     | Open     | Data synchronization issue          |
| BUG-02  | Medium   | Open     | Incorrect password error            |
| BUG-03  | Low      | Open     | Push notifications not received during app minimization |
| BUG-04  | High     | Open     | UI misalignment on smaller screens  |
| BUG-05  | Low      | Open     | Profile picture upload not working  |
| BUG-06  | Critical | Open     | App crashes on notification click   |
| BUG-07  | Medium   | Open     | Activity data not updated immediately |

---

## 5. Environment

- **OS**: macOS, Windows 10, Android, iOS
- **Browsers**: Safari, Chrome, Firefox, Edge
- **Mobile Devices**: iPhone, Android

---

## 6. Summary

**Healthify** passed the majority of the tests, with only the **Data Synchronization** feature failing. Several bugs were identified, particularly with data synchronization, notifications, and UI alignment on smaller screens. The app is functional but requires fixes before release.

---

