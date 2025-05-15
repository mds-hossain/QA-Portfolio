# Test Case for Expense Tracking

## Test Case ID: TC-01
### Summary: Verifying the addition of an expense
- **Description**: Test the functionality of adding a new expense to the application.
- **Preconditions**: User is logged in, and the app is initialized.

### Steps
| Step | Action                                     | Expected Result                        | Status |
|------|--------------------------------------------|----------------------------------------|--------|
| 1    | Navigate to the "Add Expense" button       | Button is visible and clickable        | Pass   |
| 2    | Enter expense details (amount, category)   | Fields accept valid data               | Pass   |
| 3    | Click "Save Expense"                       | Expense is saved and visible in the list | Pass   |
| 4    | Verify expense appears in the dashboard    | Expense appears in the dashboard       | Pass   |

### Expected Result
- The newly added expense is visible in the list and dashboard.

### Actual Result
- Expense added successfully, visible on the dashboard.

---

# Test Case for Dashboard

## Test Case ID: TC-02
### Summary: Verifying the financial summary in the dashboard
- **Description**: Verify that the dashboard correctly calculates and displays total expenses vs. income.
- **Preconditions**: User has added both expenses and income.

### Steps
| Step | Action                                      | Expected Result                          | Status |
|------|---------------------------------------------|------------------------------------------|--------|
| 1    | Navigate to the dashboard                  | Dashboard page is displayed              | Pass   |
| 2    | Verify total expenses and income            | The totals should match the data entered | Pass   |
| 3    | Verify the balance calculation              | The balance should be accurate           | Pass   |

### Expected Result
- The dashboard should show accurate total expenses, income, and balance.

### Actual Result
- Dashboard displayed correct financial summary.

