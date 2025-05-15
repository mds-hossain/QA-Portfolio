# Bug Report for Expensial

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
Expenses not updating on dashboard after adding new expense

---

## Description
After adding a new expense, the dashboard does not immediately reflect the updated total expenses. The issue persists until the page is refreshed.

---

## Preconditions
- User is logged into the application.
- A valid expense is added.

---

## Steps to Reproduce
| Step | Action                                     | Expected Result                        | Actual Result                |
|------|--------------------------------------------|----------------------------------------|------------------------------|
| 1    | Add a new expense                         | Expense should be added successfully   | Expense not displayed        |
| 2    | Navigate to the dashboard                 | Total expenses should be updated       | Total not updated            |
| 3    | Refresh the page                          | The total expenses appear correctly    | Pass                         |

---

## Expected Result
- Dashboard should reflect the updated expense immediately after adding.

---

## Actual Result
- The dashboard does not update until the page is refreshed.

---

## Screenshots
- [Bug Screenshot](https://link-to-screenshot)

---

## Resolution
- **Status**: Open
