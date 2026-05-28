1. Contract-Based Targets

Store contractPercentage per employee.
Base full-time target:
dailyMinutes = 493 (8h 13m)
weeklyMinutes = 2465 (41h 5m)
For part-time employees:
employeeDailyTarget = round(baseDailyMinutes * contractPercentage / 100)
employeeWeeklyTarget = round(baseWeeklyMinutes * contractPercentage / 100)
Example:
100% -> 493 min = 8h 13m
50% -> 247 min = 4h 7m
2. Flexible Attendance

No fixed late rule.
No fixed clock-in window.
No fixed clock-out earliest time.
Employees can clock in and out anytime on the same day.
Overnight shifts are not normal. If they happen exceptionally, the system should treat them as one continuous record only if explicitly allowed by admin.
3. Break Rules

Break is mandatory.
Break is unpaid.
Only one break per day.
Break can be taken anytime.
If no break is logged, the system auto-deducts the configured break minutes from work time.
If a break is logged, use actual break minutes.
Working minutes formula:
workingMinutes = clockOutDateTime - clockInDateTime - lunchBreakMinutes
4. Time Balance

Do not reset balance daily.
Maintain one continuous time bank per employee.
Show both:
positive balance = overtime credit
negative balance = short-hours debit
Carry forward balance for up to 1 year.
After 1 year, settlement/expiry should be handled by admin or payroll rules.
5. Overtime / Negative Hours

Overtime is not auto-paid.
Overtime can be converted into:
paid time, or
day off in lieu
Negative hours can be made up later.
Balance formula:
timeBalance = totalWorkedMinutes - totalTargetMinutes
If positive, it is overtime.
If negative, it is short hours.
6. Holidays and Weekends

Public holidays count as a full working day for full-time staff.
Weekend days are not counted.
Holiday target for 100% staff = 493 minutes.
Holiday target for part-time staff = contract-based proportional target.
7. Manual Attendance / Admin Adjustments

Admin can:
mark attendance manually
edit clock-in / clock-out
adjust time balance
Reason is optional, not mandatory.
Every manual change should still be stored in an audit log:
who changed it
when
what changed
If admin changes balance directly, recalculate totals and keep the adjustment visible.
8. Notifications

Notify on:
break start/end
overtime
short hours
manual attendance changes
9. Date Handling

Use full datetime, not time-only.
Attendance should normally be stored under the clock-in date.
If an exceptional overnight shift is allowed, calculate across datetimes, not calendar day parts.
10. Recommended Implementation Rules

round() target minutes to nearest minute.
Keep exact minute calculations for working time.
Store:
dailyTargetMinutes
weeklyTargetMinutes
workedMinutes
breakMinutes
overtimeMinutes
shortMinutes
timeBalanceMinutes
