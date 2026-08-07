# Test Cases for EuroTrack

> **📌 Note on Documentation:** The files within these directories are curated excerpts rather than exhaustive test suites. The 12 test cases documented below represent the major structural, financial, and access control validation points of the EuroTrack platform. They are specifically designed to demonstrate testing methodology and structural approach to QA without overwhelming the reviewer.

**Execution Date:** June 2026
**Author:** Md Shakhawat Hossain

***

## Test Case ID: TC-01
### Summary: Verifying Brutto/Netto/MwSt reverse calculation engine
* **Description**: Test the auto-calculation logic when toggling between Netto and Brutto inputs with VAT applied.
* **Preconditions**: User is logged in as Admin and is viewing a Room Card pricing panel.

### Steps

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Activate the "Brutto/Netto anzeigen" toggle. | Brutto, Netto, and MwSt fields become visible. | Pass |
| 2 | Input a Netto value and select 19% MwSt. | Brutto field auto-calculates the correct total. | Pass |
| 3 | Clear Netto, input a Brutto value, and select 7% MwSt. | Netto field auto-calculates correctly. | Pass |

### Expected Result
* Financial inputs perfectly reverse-calculate without manual saving or layout shifting.

### Actual Result
* System successfully calculated bidirectional tax brackets on blur.

![Brutto Netto UI Toggle](./assets/tc01_brutto_netto.png)

***

## Test Case ID: TC-02
### Summary: Verifying pricing mode toggle (Per Room vs. Per Bed)
* **Description**: Test the isolation of calculations when switching between room-based and bed-based pricing modes for WG room types.
* **Preconditions**: A duration with a WG room type is created.

### Steps

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Open pricing panel for a WG room card. | "Per Bed" mode is selected by default. | Pass |
| 2 | Enter "Price per Bed" and assign 4 beds. | Room Cost calculates as Price per Bed x 4. | Pass |
| 3 | Toggle to "Per Room" mode. | Previous bed inputs clear to avoid conflict; nightly price input appears. | Pass |

### Expected Result
* Pricing modes strictly segregate mathematical formulas and reset inputs upon toggling.

### Actual Result
* Pricing modes switched cleanly with accurate mathematical resets.

***

## Test Case ID: TC-03
### Summary: Verifying prorated cost calculation across month boundaries
* **Description**: Test the dashboard's ability to split financial totals when a booking spans multiple calendar months.
* **Preconditions**: A hotel booking duration exists from May 25, 2026 to June 05, 2026.

### Steps

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Navigate to the global dashboard and select "May 2026". | Hotel row displays total cost only for the 7 nights in May. | Pass |
| 2 | Switch dashboard filter to "June 2026". | Hotel row displays total cost only for the 5 nights in June. | Pass |
| 3 | Switch dashboard filter to "All Months". | Hotel row displays the combined total cost of the entire stay. | Pass |

### Expected Result
* Cost calculations strictly respect selected date boundaries without duplicating total booking values.

### Actual Result
* Dashboard prorated all totals perfectly based on the selected month filter.

***

## Test Case ID: TC-04
### Summary: Verifying Free Beds real-time calculation
* **Description**: Test the dynamic counting of unassigned bed slots across a specific time horizon.
* **Preconditions**: A DZ room (2 beds) is booked, but only 1 employee is assigned.

### Steps

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | View the main hotel row statistics. | Free Beds indicator shows "1" in red. | Pass |
| 2 | Assign a second employee to the remaining bed slot. | Free Beds indicator updates to "0". | Pass |
| 3 | Remove the first employee from their bed slot. | Free Beds indicator updates back to "1" in red. | Pass |

### Expected Result
* The system instantly calculates unassigned slots from the current date forward.

### Actual Result
* Free beds calculated accurately across all active room cards.

***

## Test Case ID: TC-05
### Summary: Verifying employee bed slot substitution (gap filling)
* **Description**: Test the logic that allows multiple employees to share a single bed slot over different dates within a parent duration.
* **Preconditions**: A 14-night booking exists. Employee A is checked in for the first 7 nights.

### Steps

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Click the bed slot currently occupied by Employee A. | System identifies a 7-night vacant gap in the slot. | Pass |
| 2 | Click the "Substitute" icon to assign Employee B to the remaining 7 nights. | A sub-arrow icon appears, indicating a shared bed slot. | Pass |
| 3 | Check the main hotel row display. | Both names appear with accurate check-in/out borders (dashed). | Pass |

### Expected Result
* The system retains the original employee and successfully nests the substitute without overwriting data.

### Actual Result
* Gap filling logic successfully generated substitution slots.

![Employee Substitution Layout](./assets/tc05_substitution.png)

***

## Test Case ID: TC-06
### Summary: Verifying Role-Based Access Control (RBAC) permissions
* **Description**: Test database row-level security and frontend UI blocking for restricted user roles.
* **Preconditions**: User is logged in as a "Viewer".

### Steps

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Attempt to edit a hotel name in the main row. | Input field is disabled or reverts changes instantly. | Pass |
| 2 | Click on a Room Card pricing panel. | Edit toggles and price input fields are hidden or disabled. | Pass |
| 3 | Attempt to change user roles in the share menu. | The share menu is blocked and inaccessible. | Pass |

### Expected Result
* Viewer roles are strictly limited to read-only access with zero mutation capabilities.

### Actual Result
* UI elements correctly locked and backend requests returned 403 Forbidden.

***

## Test Case ID: TC-07
### Summary: Verifying timeline stay overlap filtering logic
* **Description**: Test the dashboard's date-range picker to ensure only hotels with active overlaps are displayed.
* **Preconditions**: 3 hotels exist. Hotel A is active today. Hotel B is active next week. Hotel C is empty.

### Steps

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Open the Timeline Card and select the "Today" preset. | Only Hotel A is visible. | Pass |
| 2 | Select the "7 Days" preset. | Both Hotel A and Hotel B are visible. | Pass |
| 3 | Clear the timeline filter. | All 3 hotels become visible. | Pass |

### Expected Result
* The portal system precisely filters the hotel list based on stay date overlaps.

### Actual Result
* Overlap logic correctly mapped visible durations.

***

## Test Case ID: TC-08
### Summary: Verifying invoice payment date enforcement
* **Description**: Test the validation logic that prevents saving a "Paid" status without a corresponding payment date.
* **Preconditions**: An unpaid invoice exists in the left-column ledger.

### Steps

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Toggle the invoice status from UNPAID to PAID. | "Paid On" date picker appears. Save button turns grey. | Pass |
| 2 | Attempt to click the grey Save button. | Invoice does not save; system awaits date input. | Pass |
| 3 | Select a valid date in the "Paid On" picker. | Save button turns green and successfully commits to the database. | Pass |

### Expected Result
* Financial ledgers strictly enforce date dependencies for paid statuses.

### Actual Result
* Validation gate successfully blocked incomplete state saving.

![Invoice Ledger Validation](./assets/tc08_invoice_ledger.png)

***

## Test Case ID: TC-09
### Summary: Verifying mobile room card expansion UI
* **Description**: Test the responsive wrapper constraints for mobile viewports to ensure clean vertical layouts.
* **Preconditions**: App is viewed on an emulated iOS device viewport.

### Steps

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | View the collapsed mobile room card. | Displays summary pills (WG 1, EZ 5) and primary employee names. | Pass |
| 2 | Tap the room card to expand. | Transforms into a single horizontal row for configuration to save vertical space. | Pass |
| 3 | Verify employee inputs. | Check-in/out inputs stack cleanly below the bed assignment. | Pass |

### Expected Result
* Mobile UI prevents horizontal scrolling and optimizes vertical real estate.

### Actual Result
* Responsive CSS successfully collapsed detailed tables into stacked mobile cards.

***

## Test Case ID: TC-10
### Summary: Verifying multi-select company tag interactions
* **Description**: Test the custom dropdown functionality for assigning tags to hotel entries.
* **Preconditions**: User is creating or editing a hotel entry.

### Steps

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Click the Company input field. | Dropdown opens showing existing system tags. | Pass |
| 2 | Type a new company name not in the list. | "Create new tag" option appears dynamically. | Pass |
| 3 | Select multiple tags. | Dropdown remains open during selection, and tags appear as removable chips. | Pass |

### Expected Result
* The component acts as a persistent, multi-select portal without closing unexpectedly.

### Actual Result
* Custom dropdown component functioned seamlessly without native browser UI interference.

***

## Test Case ID: TC-11
### Summary: Verifying undo/redo state snapshot recovery
* **Description**: Test the time-travel pill functionality to reverse accidental data mutation.
* **Preconditions**: User is actively editing prices across multiple durations.

### Steps

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Change the total cost of a room card from 100 to 500. | New total is saved in the current snapshot. | Pass |
| 2 | Click the left Undo arrow pill. | The total cost instantly reverts to 100. | Pass |
| 3 | Click the right Redo arrow pill. | The total cost reapplies the 500 value. | Pass |

### Expected Result
* The snapshot engine reliably holds state history up to 20 steps for forgiving UI correction.

### Actual Result
* State history array successfully mapped forward and backward mutations.

***

## Test Case ID: TC-12
### Summary: Verifying Auto-Floor minimum bed price scanner
* **Description**: Test the global engine that scans all invoices to display the lowest actual bed price.
* **Preconditions**: Master dashboard indicates a manual override price of "ab 30,00 EUR / N".

### Steps

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Create a new invoice line item with a "Per Bed" rate of 25 EUR. | Scanner detects a rate lower than the manual override. | Pass |
| 2 | Save the invoice. | Master dashboard automatically drops the override and updates to "ab 25,00 EUR / N". | Pass |
| 3 | Create a new invoice using only "Total Mode" (Gesamtbetrag). | Scanner ignores this invoice; dashboard price remains 25 EUR. | Pass |

### Expected Result
* The system dynamically enforces factual pricing by auto-correcting manual overrides when cheaper standard rates are detected.

### Actual Result
* Scanner effectively located the minimum integer and updated the global state.
