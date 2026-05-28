# Flexible Shift & Time Bank Guide

This document explains how the Flexible Shift system and the Time Bank Ledger work together in the LMS application.

## 1. Manual Attendance (Admin Guide)
Use the **Manual Attendance** screen to correct missed logs or handle exceptional cases.

### Steps to Edit Attendance:
1.  **Select Employee**: Search and pick the employee.
2.  **Pick Date**: Choose the date for the correction.
3.  **Set Times**: Enter the **Clock In** and **Clock Out** times.
4.  **Lunch/Break Minutes**:
    *   **Leave Blank**: The system uses the default minimum (usually 30 minutes).
    *   **Enter Minutes**: If the employee took a longer break (e.g., 2 hours), enter `120`. This ensures their "Worked Time" is accurate.
5.  **Reason**: Provide a optional reason for the manual entry.
6.  **Save**: The system calculates the **Working Minutes** (`Duration - Break`) and updates the Time Bank automatically.

---

## 2. How the Time Bank Works
The Time Bank is an automated ledger that tracks "Extra Hours" (Credits) or "Short Hours" (Debits) based on flexible shift logic.

### Daily Target Calculation
The system determines how many minutes an employee *should* work based on:
*   **Base Target**: Set in system settings (e.g., 493 minutes per day).
*   **Contract Percentage**: Adjusted per employee (e.g., a 50% part-timer has a ~246-minute target).
*   **Weekend Rule**: Saturday and Sunday usually have a **0-minute target**.

### Daily Settlement
Every day, the system compares **Worked Minutes** vs. **Target Minutes**:
*   **Extra Hours (Credit)**: If an employee works **more** than their target, the surplus is added to their balance.
*   **Short Hours (Debit)**: If they work **less** than their target, the deficit is subtracted.
*   **Weekend Work**: Since the target is 0, **all minutes worked on a weekend are credited 100%**.

### Other Ledger Entries
*   **Public Holidays**: Employees receive a **Credit** equal to their daily target minutes (gifted time).
*   **Compensatory Off (CompOff)**: When an employee takes a day off using their balance, the target minutes for those days are **Debited**.
*   **Cash Payout**: If extra hours are paid out in cash, the equivalent time is **Debited** from the balance.

---

## Summary for Users
> **"Work extra today to save time for a day off tomorrow."**
> All changes can be tracked in the **Time Bank Ledger** within the Employee Profile.
