## Bug ID: BUG-01
- **Test Case ID**: TC-04
- **Author**: Md Shakhawat Hossain
- **OS**: macOS
- **Browser**: Safari
- **Date**: 03/03/2024
- **Priority**: High
- **Severity**: Critical

---

### Title
Data synchronization issue between web and mobile devices

### Description
Data added on the web app does not appear on the mobile app until the mobile app is manually refreshed.

### Steps to Reproduce

| Step | Action                            | Expected Result                          | Actual Result                |
|------|-----------------------------------|------------------------------------------|------------------------------|
| 1    | Add activity on the web app       | Activity should appear on mobile app     | Activity not synced          |
| 2    | Refresh the mobile app           | Activity should sync                    | Manual refresh required      |

### Expected Result
- Activity data should sync across devices without manual refresh.

### Actual Result
- Data only appears after refreshing the mobile app.

### Resolution
- **Status**: Open

---

## Bug ID: BUG-02
- **Test Case ID**: TC-02
- **Author**: Md Shakhawat Hossain
- **OS**: Windows 10
- **Browser**: Chrome
- **Date**: 02/03/2024
- **Priority**: Medium
- **Severity**: Major

---

### Title
Incorrect password error after successful login

### Description
Sometimes the app shows an incorrect password error even though the user has entered the correct password.

### Steps to Reproduce

| Step | Action                           | Expected Result                          | Actual Result                |
|------|----------------------------------|------------------------------------------|------------------------------|
| 1    | Enter valid login credentials   | User should be logged in successfully     | Error message shown          |
| 2    | Click "Login"                   | User is logged in correctly               | Incorrect password error     |

### Expected Result
- User should be logged in successfully when correct credentials are entered.

### Actual Result
- Incorrect password error appears intermittently.

### Resolution
- **Status**: Open

---

## Bug ID: BUG-03
- **Test Case ID**: TC-06
- **Author**: Md Shakhawat Hossain
- **OS**: Android
- **Browser**: Chrome
- **Date**: 04/03/2024
- **Priority**: Low
- **Severity**: Minor

---

### Title
Push notifications not received during app minimization

### Description
Users do not receive push notifications if the app is minimized while they reach a fitness milestone.

### Steps to Reproduce

| Step | Action                           | Expected Result                          | Actual Result                |
|------|----------------------------------|------------------------------------------|------------------------------|
| 1    | Minimize the app during tracking | Push notifications should be received    | No notifications received    |
| 2    | Track a fitness milestone       | Push notification should be displayed    | Notification not received    |

### Expected Result
- Push notifications should appear even when the app is minimized.

### Actual Result
- Notifications do not appear when the app is minimized.

### Resolution
- **Status**: Open

---

## Bug ID: BUG-04
- **Test Case ID**: TC-07
- **Author**: Md Shakhawat Hossain
- **OS**: macOS
- **Browser**: Firefox
- **Date**: 03/03/2024
- **Priority**: High
- **Severity**: Major

---

### Title
UI misalignment on the profile page for smaller screen sizes

### Description
The profile page UI elements do not align properly on smaller screen sizes, making it difficult to navigate.

### Steps to Reproduce

| Step | Action                           | Expected Result                          | Actual Result                |
|------|----------------------------------|------------------------------------------|------------------------------|
| 1    | Open profile page on a small screen | UI elements should be properly aligned   | Misalignment occurs          |

### Expected Result
- The UI elements should be aligned properly on small screens.

### Actual Result
- The elements do not align correctly.

### Resolution
- **Status**: Open

---

## Bug ID: BUG-05
- **Test Case ID**: TC-05
- **Author**: Md Shakhawat Hossain
- **OS**: Windows 10
- **Browser**: Edge
- **Date**: 05/03/2024
- **Priority**: Low
- **Severity**: Minor

---

### Title
Profile picture upload does not work

### Description
When trying to upload a profile picture, the app throws an error message, and the upload does not succeed.

### Steps to Reproduce

| Step | Action                           | Expected Result                          | Actual Result                |
|------|----------------------------------|------------------------------------------|------------------------------|
| 1    | Navigate to the profile page    | Profile page should load correctly       | Page loads fine              |
| 2    | Upload profile picture          | Picture should be uploaded successfully  | Upload fails with an error   |

### Expected Result
- The profile picture should be uploaded successfully.

### Actual Result
- The upload fails with an error.

### Resolution
- **Status**: Open

---

## Bug ID: BUG-06
- **Test Case ID**: TC-06
- **Author**: Md Shakhawat Hossain
- **OS**: Android
- **Browser**: Mobile App
- **Date**: 06/03/2024
- **Priority**: High
- **Severity**: Critical

---

### Title
App crashes on notification click

### Description
The app crashes when users click on a push notification to view the details.

### Steps to Reproduce

| Step | Action                           | Expected Result                          | Actual Result                |
|------|----------------------------------|------------------------------------------|------------------------------|
| 1    | Click on a notification          | The app should open the relevant screen  | App crashes                  |

### Expected Result
- The app should open without crashing.

### Actual Result
- The app crashes when the notification is clicked.

### Resolution
- **Status**: Open

---

## Bug ID: BUG-07
- **Test Case ID**: TC-04
- **Author**: Md Shakhawat Hossain
- **OS**: iOS
- **Browser**: Safari
- **Date**: 07/03/2024
- **Priority**: Low
- **Severity**: Major

---

### Title
User's activity data not updated on the dashboard

### Description
The activity data does not update immediately on the dashboard after logging an activity.

### Steps to Reproduce

| Step | Action                           | Expected Result                          | Actual Result                |
|------|----------------------------------|------------------------------------------|------------------------------|
| 1    | Log an activity on the app      | The dashboard should show the updated data | The data does not update immediately |

### Expected Result
- The dashboard should reflect updated activity data immediately.

### Actual Result
- The data does not update immediately on the dashboard.

### Resolution
- **Status**: Open

