# Test Case for Taskyfier

## Test Case ID: TC-01
### Summary: Verifying task creation functionality
- **Description**: Test the functionality of creating a new task.
- **Preconditions**: User is logged in.

### Steps

| Step | Action                                       | Expected Result                        | Status |
|------|----------------------------------------------|----------------------------------------|--------|
| 1    | Navigate to the task creation page          | Page loads correctly                   | Pass   |
| 2    | Enter valid task details (name, due date)   | Fields accept valid data               | Pass   |
| 3    | Click the "Save Task" button                | Task is saved and displayed            | Pass   |

### Expected Result
- Task is successfully created and appears in the task list.

### Actual Result
- Task was created successfully and appeared in the task list.

---

## Test Case ID: TC-02
### Summary: Verifying task editing functionality
- **Description**: Test the functionality of editing an existing task.
- **Preconditions**: User has an existing task.

### Steps

| Step | Action                                       | Expected Result                        | Status |
|------|----------------------------------------------|----------------------------------------|--------|
| 1    | Navigate to the task list                   | Task list loads correctly              | Pass   |
| 2    | Select an existing task                     | Task details are displayed             | Pass   |
| 3    | Edit the task details                       | Fields accept updated data             | Pass   |
| 4    | Click the "Save Changes" button             | Task is updated in the task list       | Pass   |

### Expected Result
- Task is successfully edited and updated in the task list.

### Actual Result
- Task was edited and updated as expected.

---

## Test Case ID: TC-03
### Summary: Verifying task deletion functionality
- **Description**: Test the functionality of deleting a task.
- **Preconditions**: User has an existing task.

### Steps

| Step | Action                                       | Expected Result                        | Status |
|------|----------------------------------------------|----------------------------------------|--------|
| 1    | Navigate to the task list                   | Task list loads correctly              | Pass   |
| 2    | Select an existing task                     | Task details are displayed             | Pass   |
| 3    | Click the "Delete" button                   | Task is removed from the list          | Pass   |

### Expected Result
- Task is successfully deleted from the task list.

### Actual Result
- Task was deleted successfully.

---

## Test Case ID: TC-04
### Summary: Verifying task notifications
- **Description**: Test if notifications are sent for tasks nearing their due date.
- **Preconditions**: User has set a task with a due date.

### Steps

| Step | Action                                       | Expected Result                        | Status |
|------|----------------------------------------------|----------------------------------------|--------|
| 1    | Set a task with a due date in the future    | Task is saved with a due date          | Pass   |
| 2    | Wait for the task to approach the due date  | Notification is sent before the due date| Pass   |

### Expected Result
- User receives a notification for the task nearing its due date.

### Actual Result
- Notification was received as expected.

---

## Test Case ID: TC-05
### Summary: Verifying task synchronization across devices
- **Description**: Test if tasks sync correctly across devices (web and mobile).
- **Preconditions**: User is logged in on both web and mobile devices.

### Steps

| Step | Action                                       | Expected Result                        | Status |
|------|----------------------------------------------|----------------------------------------|--------|
| 1    | Create a task on the web app                | Task is created                        | Pass   |
| 2    | Check if the task appears on mobile app     | Task is synced on mobile app           | Pass   |

### Expected Result
- Task should sync correctly across devices without issues.

### Actual Result
- Task synced correctly across web and mobile.

---

## Test Case ID: TC-06
### Summary: Verifying task completion functionality
- **Description**: Test if users can mark tasks as completed.
- **Preconditions**: User has a pending task.

### Steps

| Step | Action                                       | Expected Result                        | Status |
|------|----------------------------------------------|----------------------------------------|--------|
| 1    | Navigate to the task list                   | Task list loads correctly              | Pass   |
| 2    | Select an incomplete task                   | Task details are displayed             | Pass   |
| 3    | Mark the task as completed                  | Task status is updated to completed    | Pass   |

### Expected Result
- Task is marked as completed and is shown in the completed section.

### Actual Result
- Task was marked as completed successfully.

---

## Test Case ID: TC-07
### Summary: Verifying app responsiveness across devices
- **Description**: Test the app’s UI responsiveness on both desktop and mobile devices.
- **Preconditions**: User is logged in.

### Steps

| Step | Action                          | Expected Result                          | Status |
|------|---------------------------------|------------------------------------------|--------|
| 1    | Open the app on a desktop       | The app should be responsive and fit the screen | Pass   |
| 2    | Open the app on a mobile device | The app should be responsive and adapt to the smaller screen | Pass   |
| 3    | Verify elements on both devices | UI elements should be properly aligned   | Pass   |

### Expected Result
- The app should be responsive and display properly on all devices.

### Actual Result
- The app displayed correctly on both desktop and mobile devices.

---
