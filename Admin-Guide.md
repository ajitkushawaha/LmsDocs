# Workforce LMS - Admin Guide

Version: 1.0  
Last updated: March 27, 2026

## 1. Overview

Workforce LMS helps administrators:

- manage employees
- configure attendance policy
- review attendance
- approve or reject leave
- monitor notifications
- review device-change alerts

## 2. Admin Login

### Steps

1. Open the app.
2. Enter admin email.
3. Enter password.
4. Tap `Sign In`.

### Admin Login Screen
![Admin Login](file:///Users/ajitkushwhaha/Developer/App/lms/docs/images/login_screen.png)

## 3. Admin Dashboard

The dashboard shows:

- total employees
- present and absent summary
- leave summary
- quick navigation to workforce, attendance, and leave sections

### Admin Dashboard Screen
![Admin Dashboard](file:///Users/ajitkushwhaha/Developer/App/lms/docs/images/admin_dashboard.png)

## 4. Employee Management

### Add employee

1. Open `Workforce`.
2. Tap `Add Member`.
3. Enter employee details.
4. Save.

### Edit employee

1. Open `Workforce`.
2. Select employee.
3. Update details.
4. Save changes.

### Screenshot to add

- Workforce list screen
- Add employee form
- Edit employee form

## 5. Work Policy

The work policy screen controls:

- attendance mode: selfie or QR
- daily working hours
- weekly working hours
- shift start
- late after
- earliest clock-out
- overtime grace minutes
- lunch break window
- lunch minimum minutes
- office geofence
- leave entitlement totals

### Important rules

- `Shift Start` is official start time.
- `Late After` is the grace end.
- `Earliest Clock-Out` is the minimum allowed exit time.
- `Overtime Grace (Minutes)` controls when overtime begins.

### Screenshot to add

- Work policy screen - attendance protocol section
- Work policy screen - shift infrastructure section
- Work policy screen - geofencing section
- Work policy screen - leave entitlement section

## 6. QR Station

If QR attendance is enabled:

1. Open `Menu` -> `QR Station`.
2. Generate or display the office QR.
3. Place the QR in the office for employee scanning.

### Screenshot to add

- QR station screen

## 7. Leave Management

### Review leave

1. Open `Requests`.
2. Select a leave item.
3. Review employee, dates, type, and reason.
4. Approve or reject the request.

### Leave balance behavior

- balance-based leave types deduct on approval
- emergency/other behavior depends on current policy

### Screenshot to add

- Admin leave list
- Leave review modal

## 8. Attendance Records

The attendance logs screen shows:

- clock-in and clock-out entries
- present status
- short hours
- overtime
- search and filtering

### Screenshot to add

- Attendance logs screen
- Filter/search state

## 9. Employee Detail Screen

The employee detail screen shows:

- monthly attendance calendar
- present / absent / leave overview
- leave breakdown
- primary device information
- selected attendance-day device

### Device management

- first attendance device becomes primary
- if attendance comes from another device, admin receives an alert
- admin can set the selected device as primary if valid

### Employee Detail & Device Management Section
![Employee Detail Overview & Device Control](file:///Users/ajitkushwhaha/Developer/App/lms/docs/images/employee_detail.png)

## 10. Device Change Alerts

When an employee marks attendance from a different device:

- admin receives notification
- attendance can be reviewed
- primary device can be updated manually

### Security: Device Mismatch Alert & Control
![Device Authorization & Mismatch Alert](file:///Users/ajitkushwhaha/Developer/App/lms/docs/images/employee_detail.png)

## 11. Notifications

Admins may receive notifications for:

- late clock-in
- short hours recorded
- leave requests
- leave approvals/rejections
- device change alerts

### Screenshot to add

- Notifications screen for admin
- Example late clock-in alert
- Example short-hours notification

## 12. Overtime and Short Hours Policy

### Effective work start

- early arrival before shift start does not count as work time

### Late arrival

- if employee clocks in after grace end, the employee is marked late

### Short hours

- if employee clocks out after allowed time but has not completed target hours, short hours are recorded

### Overtime

- overtime starts only after overtime grace threshold
- example:
  - shift end `6:00 PM`
  - grace `60 minutes`
  - exit `6:30 PM` -> no overtime
  - exit `7:00 PM` -> 1 hour overtime

## 13. Reports and Operational Checks

Admins should regularly review:

- pending leave requests
- absent employees
- short hours
- late clock-in patterns
- device mismatch activity

### Screenshot to add

- Reports screen

## 14. Support and Operations

If a user cannot log in or attendance fails, check:

- backend is reachable
- work policy is configured correctly
- office QR is valid
- geofence location is correct
- employee device permissions are allowed



1. Break time
Employee can start and end a break from the attendance screen. The app records how long the break was and deducts it from total worked time. In attendance details, we can show worked time, break time, and final calculated hours.

2. Overtime and negative hours
The app compares the employee’s worked hours with their required target hours.
Example: if target is 6 hours and employee works 7 hours, app shows +1 hour overtime.
If target is 6 hours and employee works 5 hours, app shows 1 hour negative/short hours.

3. Vacation day balance
Vacation balance is managed through the leave system. Admin sets the total vacation allowance, and when vacation leave is approved, the app deducts it. The employee can see remaining vacation balance, and admin can now see vacation balance on employee detail.

4. Edit, correct, and fill manually
Admin can use Manual Attendance to fix missed or wrong entries. Admin can select employee, date, clock-in, clock-out, break/lunch minutes, and reason. The app previews expected hours, worked hours, break, overtime, or negative hours before saving.

### Manual Attendance Screen
![Manual Attendance Override Form](file:///Users/ajitkushwhaha/Developer/App/lms/docs/images/manual_attendance.png)

5. Work percentage scheduling
Admin sets each employee’s work percentage, for example 100%, 80%, or 50%.
The app uses that percentage to calculate the employee’s expected daily/weekly hours.

Example:

Full-time target: 8 hours
100% employee target: 8 hours
50% employee target: 4 hours
80% employee target: 6 hours 24 minutes