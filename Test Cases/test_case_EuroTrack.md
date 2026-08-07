# Test Cases for EuroTrack

> **📌 Note on Documentation:** The files within these directories are curated excerpts rather than exhaustive test suites. The 12 test cases documented below represent the major structural, financial, and access control validation points of the EuroTrack platform. They are specifically designed to demonstrate testing methodology and structural approach to QA without overwhelming the reviewer.

**Execution Date:** June 2026
**Author:** Md Shakhawat Hossain

***

## Test Case ID: TC-01
### Summary: Verifying horizontal group-by layout mutation (Dynamic Tabs)
* **Description**: Test that selecting a "Group By" parameter shifts the data grid into a horizontal tabbed view displaying the correct entity name, entry count, and aggregated group valuation.
* **Preconditions**: Multiple active hotel records spanning different parent companies, cities, and countries are populated in the system.

### Steps

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Click the "Group by Hotel" button on the advanced control workspace. | Layout mutates into horizontal tabs; each tab displays the Hotel name, a count chip of entries, and the total financial value underneath. | Pass |
| 2 | Click on a specific horizontal tab. | The main list panel filters instantly to display only the rows belonging to that selected group. | Pass |
| 3 | Toggle through "Group by Company" and "Group by City" tabs. | The horizontal tabs dynamically re-render with precise numeric values without freezing the client-side state. | Pass |

### Expected Result
* Layout correctly displays structural entity hierarchies via horizontal tabs rather than a compressed single grid view.

### Actual Result
* Horizontal tabs dynamically computed aggregated group costs and re-rendered layout smoothly.

![Horizontal Grouping Tabs](./assets/tc01_group_tabs.png)

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
| 2 | Click on a Room Card panel to trigger a pricing change. | Action is blocked; edit toggles and inputs are disabled for non-editor profiles. | Pass |
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
### Summary: Verifying real-time sync between statistics widgets and list dashboards
* **Description**: Test that filtering parameters applied on the data list immediately update the state arrays bound to the SVG charts and charts components.
* **Preconditions**: Master calculations pipeline is running with `useMemo` hooks configured for client-side evaluation.

### Steps

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Apply a multi-parameter filter isolating only "Overdue" invoices for "Munich". | Main data list instantly filters to match criteria. | Pass |
| 2 | Observe the Glowing Single-Ring Financial Donut widget at the top section. | The SVG arcs and connective elbow pointers dynamically compress to represent only the localized sub-metrics. | Pass |
| 3 | Check the Proportional Allocation Bar Chart. | Vertical month blocks drop to reflect exact expenditures for the filtered sub-array. | Pass |

### Expected Result
* Unification of data views ensures chart states sync instantaneously with the dashboard list without database refetches.

### Actual Result
* Client-side hooks successfully broadcasted state changes across list and visualization layers simultaneously.

![Widget State Synchronization](./assets/tc11_widget_sync.png)

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
