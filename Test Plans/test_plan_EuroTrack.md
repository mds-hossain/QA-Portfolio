# Test Plan for EuroTrack

> **📌 Note on Documentation:** The files within these directories are curated excerpts rather than exhaustive test suites. They are specifically designed to demonstrate my testing methodology, documentation standards, and structural approach to QA without overwhelming the reviewer.

## Version History
| Date       | Version | Changelog                           |
|------------|---------|-------------------------------------|
| 01/06/2026 | 1.0     | Initial document creation for EuroTrack |
| 05/06/2026 | 1.1     | Updates to include test schedule    |

## Created by: Md Shakhawat Hossain

---

## Contents

1. [Introduction](#1-introduction)
2. [Scope](#2-scope)
3. [Types of Tests](#3-types-of-tests)
4. [Test Results](#4-test-results)
5. [Resources & Environment](#5-resources-environment)
6. [Schedule of Tests](#6-schedule-of-tests)
7. [Summary](#7-summary)

---

## 1. Introduction

This test plan outlines the testing scope, approach, and schedule for the **EuroTrack** project, a full-stack enterprise workforce logistics, billing, and accommodation management system. The platform handles complex multi-tenant data routing, granular workspace permission levels, real-time sync states, and prorated financial calculations.

### 1.1 Range
#### 1.1.1 Areas to be tested
* **Multi-Tenant Room & Bed Management Architecture**: Verification of data boundaries across physical room cards, dynamic bed slots, and custom stepper calculations (EZ, DZ, TZ, WG).
* **Automated Financial Engine**: Validation of automated Brutto/Netto/MwSt conversions, percentage vs. fixed discount calculations, extra cost arrays, and the multi-mode invoice ledger.
* **Date Overlap & Prorated Splitting Engine**: Testing date boundary gates ensuring duration costs spanning multiple months split correctly, and checking historical timeline dashboard accuracy.
* **Role-Based Access Control (RBAC)**: Verification of workflow visibility, action blocking, and database row protection rules across distinct permissions (Superadmin, Admin, Editor, Viewer).
* **Real-Time Data Integrity**: Test validation of database persistence via custom Supabase endpoints, ensuring values persist on refresh.

#### 1.1.2 Non-tested Areas
* **Payment Gateway Rails**: Direct banking transaction clearings and merchant credit processing are out of scope. Testing terminates at internal invoice status persistence.

### 1.2 Purpose of the Tests
The goal of these tests is to achieve application stability, total financial audit accuracy, layout consistency across desktop and mobile UI viewports, and clean data isolation across multi-tenant workspaces.

---

## 2. Types of Tests

* **Multi-Tenant Security Testing**: Validation of database row-level security (RLS) to ensure users cannot view or mutate cross-workspace objects.
* **Boundary Value Analysis (BVA) & Equivalence Partitioning (EP)**: Applied to all calendar input forms to prevent out-of-bounds date selection.
* **Functional & UI Interactivity Testing**: Validation of custom multi-select tags, auto-expanding textareas, input locking gates, and hover tooltips.
* **End-to-End (E2E) Automation Testing**: Execution of regression suites written in Playwright to simulate end-to-end booking flows, validation shifts, and user role updates.
* **Cross-Device Performance Testing**: Evaluating layout changes, text wrapping behaviors, and gesture portals between desktop and mobile viewports.

---

## 3. Test Results

The test results will be compiled into a detailed report that documents the status of each feature tested, pass/fail ratios, and any critical defects found related to data splitting, RBAC, or real-time sync states.

---

## 4. Resources & Environment

### 4.1 Testing Tools
* **Bug Tracking Tool**: Jira
* **Test Case Management**: TestRail
* **API Testing**: Postman
* **Automation Tool**: Playwright (TypeScript) for E2E and regression testing

### 4.2 Testing Devices & Environment
* **Web Deployment Engine**: Vercel Production Preview
* **Database Platform**: Supabase Postgres with Realtime WebSockets
* **OS**: macOS, Windows 11 Enterprise
* **Browsers**: Chrome, Firefox, Safari
* **Mobile Emulation**: iOS, Android viewports

---

## 5. Schedule of Tests

| Module Name | Priority | Date | Time | Tester |
| :--- | :--- | :--- | :--- | :--- |
| RBAC Security & RLS Gates | High | 10/06/2026 | 4 hrs | Md Shakhawat |
| Date Splitting & Financial Math | High | 11/06/2026 | 5 hrs | Md Shakhawat |
| Room Card & Bed Slot Logistics | Medium | 12/06/2026 | 3 hrs | Md Shakhawat |
| Invoice Ledger Interaction | Medium | 13/06/2026 | 4 hrs | Md Shakhawat |
| Search Scopes & Tags | Low | 14/06/2026 | 2 hrs | Md Shakhawat |

---

## 6. Summary

This master test plan acts as the operational framework for EuroTrack quality management. Through automated Playwright scripting and targeted manual edge-case testing, it guarantees total system compliance with enterprise accounting rules, robust security parameters, and strict layout requirements across all user roles.

---
