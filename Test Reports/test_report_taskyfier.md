
# Test Report for Taskyfier

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

This report summarizes the results of the testing activities conducted on **Taskyfier**, a task management application. Testing focused on core features such as task creation, editing, deletion, and synchronization across devices.

---

## 2. Test Results

| Module Name            | Status   | Defects Found |
|------------------------|----------|---------------|
| Task Creation          | Passed   | 0             |
| Task Editing           | Passed   | 0             |
| Task Deletion          | Passed   | 0             |
| Task Notifications     | Failed   | 1             |
| Data Synchronization   | Failed   | 1             |

---

## 3. Metrics

- **Total Test Cases**: 7
- **Executed Test Cases**: 7
- **Passed**: 5
- **Failed**: 2

---

## 4. Defects Found

| Bug ID  | Severity | Status   | Description                          |
|---------|----------|----------|--------------------------------------|
| BUG-01  | High     | Open     | Task notifications not sent for upcoming deadlines |
| BUG-02  | High     | Open     | Tasks not syncing between web and mobile devices |

---

## 5. Environment

- **OS**: macOS, Windows 10
- **Browsers**: Safari, Chrome
- **Mobile Devices**: iOS, Android

---

## 6. Summary

**Taskyfier** is a task management application that has been tested successfully in terms of core functionality. However, the notifications and synchronization issues need to be fixed before deployment. All other features worked as expected.

---

