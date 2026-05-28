# LMS Project Operational Workflow
> **Client Preview Version** | Attendance, Leave, and Admin Oversight

---

## 1. Employee Workday Flow (with Lunch Logic)
This diagram captures the employee experience from arrival through clock-in, managing lunch breaks, requesting emergency leave if needed, and final clock-out.

```mermaid
flowchart TD
    Start((Start)) --> Arrival[Employee arrives at office]
    Arrival --> ClockIn[Clock in with photo + GPS]
    ClockIn --> Work[Working Status]
    
    Work --> BreakDecision{Record Break?}
    BreakDecision -- Manual --> StartBreak[Start Break + Geo-tag]
    StartBreak --> MinWait[Wait for min 30m]
    MinWait --> EndBreak[End Break + Geo-verification]
    EndBreak --> Work
    
    BreakDecision -- No Record --> AutoDeduct[Auto-deduct 30m at Clock-out]
    AutoDeduct --> Work
    
    Work --> EmergencyCheck{Leave Early?}
    EmergencyCheck -- Yes --> RequestLeave[Request approval]
    RequestLeave --> AdminReview[Admin reviews]
    AdminReview -- Rejected --> Locked[Locked - Retry Request]
    Locked --> RequestLeave
    AdminReview -- Approved --> Approved[Permission Granted]
    Approved --> ClockOut
    
    EmergencyCheck -- No --> ClockOut[Clock out + Hour Calculation]
    ClockOut --> Finish((End of Day))
```

### Key Logic Highlights:
*   **Lunch Deduction**: To simplify administration, if no break is manually logged, the system automatically deducts **30 minutes** from the total working time.
*   **Security**: All clock-in/out and break events are geo-fenced and verified against the registered workplace coordinates.

---

## 2. Admin Management & Oversight
While employees focus on their logs, the Admin maintains system health through configuration, real-time monitoring, and proactive auditing.

```mermaid
flowchart LR
    Config[Config Daily workinh hour & Geo-fence]
    Monitor[Monitor Live Attendance Dashboard]
    Alerts[Receive Auto-alerts: Late/Overtime]
    Review[Review & Approve Leave Requests]
    Audit[Audit/Edit Attendance Records]
    Export[Export Monthly CSV Reports]

    Config --> Monitor
    Monitor --> Alerts
    Monitor --> Review
    Monitor --> Audit
    Audit --> Export
```

---

## 3. Planned Leave Lifecycle
Employees can request planned leaves (Vacation, Sick Leave, etc.) in advance. This process ensures the admin can manage workforce availability before the workday begins.

```mermaid
flowchart TD
    Submit[Employee submits planned leave]
    AdminAwaits[Admin receives notification]
    AdminAction{Approve or Reject?}
    Reject[Notify Employee + Feedback]
    Approve[System updates attendance schedule]
    Notification[Push notification sent to Employee]

    Submit --> AdminAwaits --> AdminAction
    AdminAction -->|Reject| Reject
    AdminAction -->|Approve| Approve --> Notification
```

---
*&copy; 2026 LMS Platform Documentation. Generated for Client Review.*

Connect your project to Expo
Run the following command connect your project to Expo. This allows you to use our services:
npx eas-cli@latest init --id 2154ce41-8afe-4b47-9c4b-096871b23a61

Build and submit to the app stores
Run the following command to create Android and iOS builds, then submit them to the app stores.

npx eas-cli@latest build --platform all --auto-submit