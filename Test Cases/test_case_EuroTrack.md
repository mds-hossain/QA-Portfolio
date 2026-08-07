# Test Cases for EuroTrack

> **📌 Note on Documentation:** The files within these directories are curated excerpts rather than exhaustive test suites. The 15 test cases documented below represent the major structural, financial, and access control validation points of the EuroTrack platform. They are specifically designed to demonstrate my testing methodology, documentation standards, and structural approach to QA without overwhelming the reviewer.
>
> 💡 **Glossary for International Reviewers:**
> * **Netto [Net]:** The baseline price of a service or item before tax is applied.
> * **MwSt [Mehrwertsteuer / VAT]:** Value Added Tax applied as a percentage (typically 7% or 19% in German logistics/accommodation context).
> * **Brutto [Gross]:** The final total price inclusive of tax (Netto + calculated MwSt amount).

**Execution Date:** June 2026
**Author:** Md Shakhawat Hossain

---

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

![Horizontal Grouping Tabs](./assets/screenshot_tc01_group_tabs.png)

---

## Test Case ID: TC-02
### Summary: Verifying user-specific bookmark state isolation
* **Description**: Test that bookmarking a hotel row is saved exclusively to the active user's session profile and does not bleed into the global state for other authenticated users.
* **Preconditions**: User A and User B have separate accounts. A specific hotel record exists and is currently unbookmarked.

### Steps
| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Log in as User A and click the Bookmark star icon on the hotel row. | The star fills (active state), and the UI updates locally. | Pass |
| 2 | Log out User A, log in as User B, and navigate to the exact same hotel row. | The Bookmark star is empty (inactive state) for User B. | Pass |
| 3 | User B clicks the Bookmark star. Log back in as User A and un-bookmark the hotel. | User A's un-bookmark action does not affect User B's active bookmark. | Pass |

### Expected Result
* Bookmarks are strictly relational to the active `user_id` and do not alter the global object state across different tenant views.

### Actual Result
* The database properly isolated bookmark states by user ID, preventing cross-user UI bleeding.

![User Bookmark Isolation](./assets/screenshot_tc02_bookmarks.png)

---

## Test Case ID: TC-03
### Summary: Verifying monthly financial split and dynamic visibility engine
* **Description**: Test complex month-boundary logical gates. Ensure a hotel row appears in a specific month if it has overlapping stay durations OR associated invoices. Verify that an invoice cost physically shifts across chronological month boundaries based on lifecycle state updates (Creation vs. Paid dates).
* **Preconditions**: A hotel record possesses a duration across April and May. An invoice is created in April, with a due date in May.

### Steps
| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Navigate to the "April 2026" dashboard view. | The hotel row is visible. The invoice cost aggregates strictly into April's calculations based on its creation date. | Pass |
| 2 | Open the billing panel, change the payment status from Unpaid to Paid, and assign a payment execution date in "June 2026". | The cost balance is instantly deducted from the April and May ledger states. | Pass |
| 3 | Switch the dashboard month filter to "June 2026". | The hotel remains visible because of the transaction linkage, and the cash volume displays under June's cleared totals. | Pass |

### Expected Result
* Financial allocation accurately shifts ledger balances completely into the payment execution month, while retaining hotel row context across overlapping timelines.

### Actual Result
* Prorated rows and floating costs re-anchored flawlessly to the designated target month.

![Monthly Split Engine](./assets/screenshot_tc03_month_split.png)

---

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

![Free Beds Logic](./assets/screenshot_tc04_free_beds.png)

---

## Test Case ID: TC-05
### Summary: Verifying employee bed slot substitution (gap filling)
* **Description**: Test the logic that allows multiple employees to share a single bed slot over different dates within a parent duration without overwriting active rows.
* **Preconditions**: A 14-night booking exists. Employee A is checked in for the first 7 nights.

### Steps
| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Click the bed slot currently occupied by Employee A. | System identifies a 7-night vacant gap in the slot. | Pass |
| 2 | Click the "Substitute" icon to assign Employee B to the remaining 7 nights. | A sub-arrow icon appears, indicating a shared bed slot. | Pass |
| 3 | Check the main hotel row display. | Both names appear with accurate check-in/out borders (dashed). | Pass |

### Expected Result
* The system retains the original employee records and nests the sub-stay securely within the timeline gap.

### Actual Result
* Gap filling logic successfully generated substitution slots without mutating prior assignments.

![Employee Substitution Layout](./assets/screenshot_tc05_substitution.png)

---

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

![RBAC Locked UI](./assets/screenshot_tc06_rbac_locks.png)

---

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

![Timeline Filtering](./assets/screenshot_tc07_timeline_filter.png)

---

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

![Invoice Ledger Validation](./assets/screenshot_tc08_invoice_ledger.png)

---

## Test Case ID: TC-09
### Summary: Verifying mobile room card expansion UI
* **Description**: Test the responsive wrapper constraints for mobile viewports to ensure clean vertical layouts.
* **Preconditions**: App is viewed on an emulated mobile viewport.

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

![Mobile View Wrapper](./assets/screenshot_tc09_mobile_wrapper.png)

---

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

![Multi-Select Tags](./assets/screenshot_tc10_company_tags.png)

---

## Test Case ID: TC-11
### Summary: Verifying real-time sync between statistics widgets and list dashboards
* **Description**: Test that filtering parameters applied on the data list immediately update the state arrays bound to the SVG charts and visual components.
* **Preconditions**: Master calculations pipeline is running with client-side hooks configured.

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

![Widget State Synchronization](./assets/screenshot_tc11_widget_sync.png)

---

## Test Case ID: TC-12
### Summary: Verifying Auto-Floor minimum bed price scanner
* **Description**: Test the global engine that scans all invoices to display the lowest actual bed price.
* **Preconditions**: Master dashboard indicates a manual override price of "ab 30,00 EUR / N".

### Steps
| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Create a new invoice line item with a "Per Bed" rate of 25 EUR. | Scanner detects a rate lower than the manual override. | Pass |
| 2 | Save the invoice. | Master dashboard automatically drops the override and updates to "ab 25,00 EUR / N". | Pass |
| 3 | Create a new invoice using only "Total Mode" (Gesamtbetrag [Total Amount]). | Scanner ignores this invoice; dashboard price remains 25 EUR. | Pass |

### Expected Result
* The system dynamically enforces factual pricing by auto-correcting manual overrides when cheaper standard rates are detected.

### Actual Result
* Scanner effectively located the minimum integer and updated the global state.

![Auto Floor Engine](./assets/screenshot_tc12_auto_floor.png)

---

## Test Case ID: TC-13
### Summary: Verifying Invoice Ledger dual-mode financial calculation
* **Description**: Test the dual-mode math engine (Total vs. Detailed input) to ensure Netto, Brutto, and MwSt relationships balance correctly.
* **Preconditions**: User is editing an invoice record inside the billing tab.

### Steps
| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Activate "Total Mode". Input a Netto [Net] value and select 19% MwSt [VAT]. | The Brutto [Gross] field locks and automatically displays the calculated total with tax. | Pass |
| 2 | Clear fields, toggle mode, input a Brutto [Gross] value and select 7% MwSt [VAT]. | The Netto [Net] field reverse-calculates to show the exact baseline price prior to tax. | Pass |
| 3 | Switch to "Detailed Mode" and inject distinct numeric rows for line item accommodations. | The system aggregates individual line items accurately into a master invoice block, syncing the main view. | Pass |

### Expected Result
* Mathematical boundaries lock input fields effectively during compilation to prevent mixed billing entry collisions.

### Actual Result
* Bidirectional calculation gates enforced perfect accounting precision across input schemas.

![Invoice Ledger Math Engine](./assets/screenshot_tc13_invoice_math.png)

---

## Test Case ID: TC-14
### Summary: Verifying data grid sorting orientations (Ascending & Descending)
* **Description**: Test that multi-parameter filters and header sorting columns properly restructure relational record views on the client side.
* **Preconditions**: Test rows are populated with variable financial sums, creation dates, and alphabetic names.

### Steps
| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Click the "Total Cost" header cell once. | The data grid rows arrange sequentially in Ascending order. | Pass |
| 2 | Click the "Total Cost" header cell a second time. | The row hierarchy instantly reverses into Descending configuration. | Pass |
| 3 | Combine sorting with an active global string filter search. | The data array preserves the string scope while successfully updating the structural sorting direction. | Pass |

### Expected Result
* Multi-parameter search terms and bidirectional column filters execute dynamically without layout clipping.

### Actual Result
* Client-side array manipulation hooks reordered row keys securely.

![Global Search and Sort](./assets/screenshot_tc14_search_sort.png)

---

## Test Case ID: TC-15
### Summary: Verifying Export Studio layout filtering and sheet compilation
* **Description**: Test the dynamic reporting module for PDF and structured spreadsheet (XLSX) binary generation.
* **Preconditions**: Data filters are actively configured on the primary ledger workspace.

### Steps
| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Launch the Export Studio menu block and deselect custom column tags (e.g., Address, Phone). | The live structural preview panel alters to hide the filtered structural columns. | Pass |
| 2 | Click the "Export PDF" trigger. | A clean, print-ready layout document compiles instantly adhering strictly to the active view. | Pass |
| 3 | Click the "Export Excel" spreadsheet option. | An XLSX binary download initializes containing clean matching cell structures for accounting integrations. | Pass |

### Expected Result
* Binary compilation engines extract only active, visibility-enabled data arrays for output reporting.

### Actual Result
* Custom column filters mapped flawlessly to generated file formats.

![Export Studio Preview](./assets/screenshot_tc15_export_studio.png)
