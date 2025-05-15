
# Bug Report for Taskyfier

## Bug ID: BUG-01
- **Test Case ID**: TC-04
- **Author**: Md Shakhawat Hossain
- **OS**: macOS
- **Browser**: Safari
- **Date**: 05/04/2024
- **Priority**: High
- **Severity**: Critical

---

### Title
Task notifications not sent for upcoming deadlines

### Description
Notifications are not sent for tasks that are approaching their due date.

### Steps to Reproduce

| Step | Action                            | Expected Result                          | Actual Result                |
|------|-----------------------------------|------------------------------------------|------------------------------|
| 1    | Create a task with a due date    | Task is saved and notification set       | No notification sent         |
| 2    | Wait for the task to near due date| Notification should be sent              | No notification received     |

### Expected Result
- Notification should be sent when the task is approaching its deadline.

### Actual Result
- Notification is not sent as expected.

### Resolution
- **Status**: Open

---

## Bug ID: BUG-02
- **Test Case ID**: TC-02
- **Author**: Md Shakhawat Hossain
- **OS**: Windows 10
- **Browser**: Chrome
- **Date**: 06/04/2024
- **Priority**: Medium
- **Severity**: Major

---

### Title
Tasks not syncing between web and mobile devices

### Description
Tasks added on the web app are not appearing on the mobile app until the app is manually refreshed.

### Steps to Reproduce

| Step | Action                            | Expected Result                          | Actual Result                |
|------|-----------------------------------|------------------------------------------|------------------------------|
| 1    | Add task on the web app          | Task should sync on mobile app           | Task not synced              |
| 2    | Refresh mobile app               | Task should appear correctly             | Manual refresh required      |

### Expected Result
- Task should sync automatically across devices.

### Actual Result
- Task only appears after refreshing the mobile app.

### Resolution
- **Status**: Open

---

## Bug ID: BUG-03
- **Test Case ID**: TC-06
- **Author**: Md Shakhawat Hossain
- **OS**: Android
- **Browser**: Chrome
- **Date**: 07/04/2024
- **Priority**: Low
- **Severity**: Minor

---

### Title
Task due date is not updating when modified

### Description
When a user edits a task's due date, the updated date is not reflected in the task list.

### Steps to Reproduce

| Step | Action                            | Expected Result                          | Actual Result                |
|------|-----------------------------------|------------------------------------------|------------------------------|
| 1    | Edit task due date               | Updated date should be reflected         | Due date not updated         |
| 2    | Save changes                     | Updated due date should appear in task list | Old date still visible       |

### Expected Result
- The task due date should update correctly in the task list.

### Actual Result
- The due date is not updated in the task list.

### Resolution
- **Status**: Open

---

## Bug ID: BUG-04
- **Test Case ID**: TC-07
- **Author**: Md Shakhawat Hossain
- **OS**: macOS
- **Browser**: Firefox
- **Date**: 08/04/2024
- **Priority**: Medium
- **Severity**: Major

---

### Title
UI misalignment on the task list page

### Description
Some UI elements, such as the task name and due date, are misaligned on the task list page.

### Steps to Reproduce

| Step | Action                            | Expected Result                          | Actual Result                |
|------|-----------------------------------|------------------------------------------|------------------------------|
| 1    | Open the task list page          | Page should load with proper alignment   | Misalignment occurs          |
| 2    | View task details                | Task details should be aligned properly | Misalignment of text         |

### Expected Result
- Task list and task details should be aligned correctly.

### Actual Result
- Misalignment of UI elements occurred.

### Resolution
- **Status**: Open

---

## Bug ID: BUG-05
- **Test Case ID**: TC-04
- **Author**: Md Shakhawat Hossain
- **OS**: Windows 10
- **Browser**: Edge
- **Date**: 09/04/2024
- **Priority**: High
- **Severity**: Critical

---

### Title
App crashes when clicking on notification

### Description
When users click on a task notification, the app crashes unexpectedly.

### Steps to Reproduce

| Step | Action                            | Expected Result                          | Actual Result                |
|------|-----------------------------------|------------------------------------------|------------------------------|
| 1    | Click on a task notification     | Task details page should open without issue | App crashes                  |

### Expected Result
- Task details should open without crashing the app.

### Actual Result
- App crashes when the notification is clicked.

### Resolution
- **Status**: Open

---

### Bug ID: BUG-06
- **Test Case ID**: TC-06
- **Author**: Md Shakhawat Hossain
- **OS**: Android
- **Browser**: Mobile App
- **Date**: 10/04/2024
- **Priority**: Low
- **Severity**: Minor

---

### Title
Completed tasks not showing in the completed section

### Description
Tasks marked as completed are not displayed in the "Completed" section.

### Steps to Reproduce

| Step | Action                            | Expected Result                          | Actual Result                |
|------|-----------------------------------|------------------------------------------|------------------------------|
| 1    | Mark task as completed            | Task should appear in the completed section | Task does not appear         |
| 2    | View completed section            | Task should be visible                   | Task not shown               |

### Expected Result
- Task should appear in the "Completed" section.

### Actual Result
- Task does not appear in the "Completed" section.

### Resolution
- **Status**: Open

---
