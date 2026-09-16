# Healthcare Clinic Booking Platform — Manual Testing Documentation

## 📋 Overview
This repository contains the manual testing deliverables for the **Healthcare Clinic Booking Platform**, developed as part of the **DEPI (Digital Egypt Pioneers Initiative)** Software Testing track.

Testing was conducted against the project's SRS document (v1.0.0) and covers two core modules:

| Module | Requirement ID |
|---|---|
| Patient Authentication | REQ-FUN-02 |
| Appointment Dashboard & Cancellation | REQ-FUN-07 |

## 👤 Tester
**Omar Ahmed**

## 👥 Project Team
Omar Ahmed, Youil, Mohamed Shaaban, Omar Mostafa, Mohamed Hani

**Supervised by:** Eng. Ahmed Sayed (DEPI Instructor)

## 📁 Repository Structure

| Folder / File | Description |
|---|---|
| `Requirments/` | SRS document and requirement specs |
| `Test_Case/` | Full test case suite (30 test cases) |
| `Bugs_Reports/` | Detailed bug reports for defects found |
| `README.md` | Project documentation |

## ✅ Test Coverage

### 1. Authentication & Access Control (15 test cases)
- Valid / invalid login (email & phone)
- Empty field validation
- Account lockout after 3 failed attempts + 15-minute cooldown
- Failed-attempt counter reset on successful login
- Case-insensitive email handling
- Password exposure check (console / localStorage / network)
- SQL / script injection protection

### 2. Post-Booking Lifecycle Management (15 test cases)
- Cancel button availability rules (24-hour cutoff, edge cases at 23h59m / 24h01m)
- Cancellation confirmation flow (modal confirm / dismiss)
- Slot availability after cancellation
- Dashboard tab behavior (Upcoming / Past / Cancelled)
- Empty-state handling
- Data persistence after page reload

## 🐞 Key Defects Found

| Bug ID | Severity | Summary |
|---|---|---|
| HEAL-236 | High | Passwords stored as **plain text** in localStorage (`carenest_users`) |
| HEAL-238 | High | Cancelled slots don't revert to "Available" — blocks re-booking |
| HEAL-237 | High | Cancel button stays active for appointments within 24 hours (missing restriction & tooltip) |
| HEAL-235 | Medium | No client-side required-field validation on the login form |

Each bug report includes steps to reproduce, expected vs. actual results, severity, and linked test case IDs.

## 🛠️ Testing Approach
- **Type:** Manual, black-box testing
- **Technique:** Positive & negative test design, boundary value analysis (24-hour cutoff edge cases), security-focused checks (data exposure, injection)
- **Traceability:** Every bug report is linked back to the test case(s) that exposed it

## 📌 Status
Testing complete for assigned modules. Reported bugs pending developer fixes and retest.
