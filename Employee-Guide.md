# Workforce LMS - Employee Guide

Version: 1.0  
Last updated: March 27, 2026

## 1. Overview

Workforce LMS helps employees:

- clock in and clock out
- scan office QR or use selfie attendance
- start and end breaks
- request leave
- view attendance history
- receive notifications

## 2. Login

### Steps

1. Open the Workforce LMS app.
2. Enter your Employee ID.
3. Enter your password.
4. Tap `Sign In`.

### Employee Login Screen
![Login Screen](file:///Users/ajitkushwhaha/Developer/App/lms/docs/images/login_screen.png)

## 3. Home Screen

The home screen shows:

- clock-in time
- time left or overtime
- current attendance mode
- break window
- clock-in / clock-out actions

### Employee Home Screen & Active Shift
![Employee Home Screen](file:///Users/ajitkushwhaha/Developer/App/lms/docs/images/employee_home.png)

## 4. Clock In

### QR mode

1. Go to the home screen.
2. Tap `Scan Station QR`.
3. Scan the office QR code.
4. Allow location permission if asked.
5. Attendance will be recorded.

### Selfie mode

1. Go to the home screen.
2. Tap `Clock In Now`.
3. Capture the attendance selfie.
4. Allow location permission if asked.
5. Attendance will be recorded.

### Important rules

- Clock-in before shift start is blocked.
- Clock-in within grace time is allowed.
- Clock-in after grace time is allowed but marked late.
- Early arrival before official shift start does not reduce the work countdown.

### Screenshot to add

- QR clock-in screen
- Selfie clock-in screen
- Success message after clock-in
- Late clock-in info message

## 5. Time Left and Overtime

### Time Left

- Countdown starts from official shift start.
- If an employee clocks in early, the app shows `Shift starts at ...` until the shift starts.
- Time left is based on required daily working hours.

### Overtime

- Overtime is not counted immediately after shift end.
- Overtime is calculated only after the configured overtime grace period.
- If the grace is 60 minutes and shift ends at 6:00 PM:
  - exit at 6:30 PM -> no overtime
  - exit at 7:00 PM -> 1 hour overtime

### Shift Progress & Time Bank Widget
![Shift Progress & Time Bank](file:///Users/ajitkushwhaha/Developer/App/lms/docs/images/employee_home.png)

## 6. Clock Out

### Steps

1. Go to the home screen.
2. Tap `Terminate Shift`.
3. In QR mode, scan the office QR.
4. Allow location permission if asked.
5. Confirm the action.

### Important rules

- Clock-out before the earliest allowed clock-out time is blocked.
- Clock-out after the allowed time is permitted.
- If target hours are incomplete, short hours are recorded.
- In QR mode, office QR is required for clock-out.
- Clock-out location must match the office geofence.

### Screenshot to add

- Clock-out confirmation dialog
- QR clock-out screen
- Short-hours success message

## 7. Break

### Steps

1. On the home screen, tap `Start Break`.
2. After returning, tap `End Break`.

### Important rules

- Break can only be started during the configured break window.
- Work countdown pauses during an active break.

### Screenshot to add

- Break card before start
- Break card while active

## 8. Attendance History

This screen shows:

- monthly attendance calendar
- present / absent / leave indicators
- total worked hours
- overtime
- selected day details

### Screenshot to add

- Attendance history screen
- Attendance history calendar with selected date detail

## 9. Leave Requests

### Steps

1. Open the `Leaves` tab.
2. Tap `Request` or `New`.
3. Select leave type.
4. Select start and end dates.
5. Enter the reason.
6. Tap `Submit Application`.

### Leave types

- Vacation
- Sick
- Comp Off
- Emergency

### Screenshot to add

- Employee leaves dashboard
- Leave request form
- Submitted leave card

## 10. Notifications

Employees receive notifications for:

- leave approval or rejection
- attendance alerts
- device/security alerts if configured

### Screenshot to add

- Notifications screen
- Example push notification

## 11. Profile

The profile screen allows employees to:

- view identity details
- update profile photo
- change password
- open privacy policy
- log out

### Screenshot to add

- Employee profile screen

## 12. Troubleshooting

### I cannot clock in

Check:

- you are within office location
- office QR is correct
- camera/location permission is allowed
- shift has started

### I cannot clock out

Check:

- earliest clock-out time has been reached
- office QR is correct
- you are within office location
- active break is ended

### My device changed

- attendance may still work depending on policy
- admin may receive a device-change alert

## 13. Support

For account, attendance, or leave issues, contact your administrator.
