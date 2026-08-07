# Test Case for Healthify

## Test Case ID: TC-01
### Summary: Verifying the registration process
- **Description**: Test the user registration functionality to ensure smooth registration.
- **Preconditions**: User is on the registration page.

### Steps

| Step | Action                                       | Expected Result                        | Status |
|------|----------------------------------------------|----------------------------------------|--------|
| 1    | Navigate to the registration page           | Registration page should load          | Pass   |
| 2    | Enter valid details (name, email, password) | Fields accept valid data               | Pass   |
| 3    | Click the "Register" button                 | User should be registered and redirected | Pass   |

### Expected Result
- The user is successfully registered and redirected to the dashboard.

### Actual Result
- The registration was successful and the user was redirected as expected.

---

## Test Case ID: TC-02
### Summary: Verifying user login functionality
- **Description**: Test the login process to ensure the user can log in correctly.
- **Preconditions**: User is registered and has valid login credentials.

### Steps

| Step | Action                                | Expected Result                         | Status |
|------|---------------------------------------|-----------------------------------------|--------|
| 1    | Open the login page                  | Login page loads                        | Pass   |
| 2    | Enter registered email and password  | Login credentials are accepted          | Pass   |
| 3    | Click "Login"                        | User is redirected to the dashboard     | Pass   |

### Expected Result
- The user successfully logs in and is directed to the homepage.

### Actual Result
- Login was successful, and the user was redirected as expected.

---

## Test Case ID: TC-03
### Summary: Verifying activity tracking functionality
- **Description**: Test the activity tracking feature to ensure activities can be logged.
- **Preconditions**: User is logged in.

### Steps

| Step | Action                             | Expected Result                         | Status |
|------|------------------------------------|-----------------------------------------|--------|
| 1    | Navigate to the activity log page | Activity log page loads correctly       | Pass   |
| 2    | Enter activity details (type, duration, etc.)   | Details are accepted               | Pass   |
| 3    | Save the activity                  | Activity is saved and displayed         | Pass   |

### Expected Result
- Activity is logged and displayed in the user's activity history.

### Actual Result
- The activity was successfully saved and displayed.

---

## Test Case ID: TC-04
### Summary: Verifying data synchronization across devices
- **Description**: Ensure data syncs across multiple devices.
- **Preconditions**: User is logged in on both web and mobile devices.

### Steps

| Step | Action                            | Expected Result                          | Status |
|------|-----------------------------------|------------------------------------------|--------|
| 1    | Log activity on web app          | Activity is logged                       | Pass   |
| 2    | Switch to mobile app             | Activity should appear on the mobile app | Fail   |
| 3    | Refresh mobile app               | The activity syncs and appears correctly | Pass   |

### Expected Result
- Activity should sync immediately across devices.

### Actual Result
- Activity only syncs after a manual refresh on mobile.

---

## Test Case ID: TC-05
### Summary: Verifying profile editing functionality
- **Description**: Test the ability to update user profile information.
- **Preconditions**: User is logged in.

### Steps

| Step | Action                              | Expected Result                          | Status |
|------|-------------------------------------|------------------------------------------|--------|
| 1    | Navigate to the profile page       | Profile page loads correctly             | Pass   |
| 2    | Edit profile details               | Profile details are updated correctly    | Pass   |
| 3    | Save the profile changes           | Profile is updated and saved             | Pass   |

### Expected Result
- User's profile information is updated successfully.

### Actual Result
- The profile information was updated as expected.

---

## Test Case ID: TC-06
### Summary: Verifying notifications functionality
- **Description**: Test if notifications are sent to the user based on fitness milestones.
- **Preconditions**: User has set a fitness goal.

### Steps

| Step | Action                               | Expected Result                           | Status |
|------|--------------------------------------|-------------------------------------------|--------|
| 1    | Set a fitness goal                  | Goal is set successfully                  | Pass   |
| 2    | Achieve a fitness milestone         | User receives a notification              | Pass   |
| 3    | Check the notification on mobile    | Notification is displayed correctly       | Pass   |

### Expected Result
- User receives notifications for fitness milestones.

### Actual Result
- Notifications are sent and displayed as expected.

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

