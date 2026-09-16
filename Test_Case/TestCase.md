# Test Cases — Healthcare Clinic Booking Platform

## 📋 Overview
This folder contains the full manual test case suite for the **Healthcare Clinic Booking Platform**, covering the two modules assigned to Omar Ahmed as part of the DEPI Software Testing track:

- **Authentication & Access Control** (REQ-FUN-02)
- **Post-Booking Lifecycle Management** (REQ-FUN-07)

**Total test cases:** 30
**Tester:** Omar Ahmed

## 🔐 Module 1 — Authentication & Access Control (TC 1–15)

| # | Test Case | Result |
|---|---|---|
| 1 | Verify login with correct email and password | Pass |
| 2 | Verify login with an unregistered email | Pass |
| 3 | Verify login with correct email and wrong password | Pass |
| 4 | Verify submission with email/phone field empty | Fail |
| 5 | Verify submission with password field empty | Fail |
| 6 | Verify submission with both fields empty | Fail |
| 7 | Verify two consecutive wrong attempts don't lock the account | Pass |
| 8 | Verify third consecutive wrong attempt locks the account | Pass |
| 9 | Verify login attempt while account is locked | Pass |
| 10 | Verify login succeeds after the 15-minute lockout expires | Pass |
| 11 | Verify failed-attempt counter resets after a successful login | Pass |
| 12 | Verify password isn't exposed in console/localStorage/network | Fail |
| 13 | Verify SQL/script injection in login fields is rejected safely | Pass |
| 14 | Verify email field is not case-sensitive | Pass |
| 15 | Verify login with correct phone number and password | Pass |

## 📅 Module 2 — Post-Booking Lifecycle Management (TC 16–30)

| # | Test Case | Result |
|---|---|---|
| 16 | Verify already-cancelled booking has no active Cancel option | Pass |
| 17 | Verify Cancel button is enabled when appointment is more than 24h away | Pass |
| 18 | Verify Cancel button is disabled when appointment is within 24h | Fail |
| 19 | Verify behavior when appointment is exactly 24h away | Fail |
| 20 | Verify Cancel button is enabled just past the 24h mark (24h01m) | Pass |
| 21 | Verify Cancel button is disabled just before the 24h mark (23h59m) | Fail |
| 22 | Verify confirming cancellation through the modal updates status | Pass |
| 23 | Verify closing the modal without confirming leaves booking unchanged | Pass |
| 24 | Verify slot reverts to Available after cancellation | Fail |
| 25 | Verify cancelling one booking doesn't affect others | Pass |
| 26 | Verify empty state when there are no upcoming bookings | Pass |
| 27 | Verify empty state when there are no past/cancelled bookings | Pass |
| 28 | Verify dashboard state persists after page reload | Pass |
| 29 | Verify Past/Cancelled tab shows past and cancelled bookings | Pass |
| 30 | Verify Upcoming tab shows only future bookings | Pass |

## 📊 Summary

| Metric | Value |
|---|---|
| Total test cases | 30 |
| Passed | 24 |
| Failed | 6 |
| Priority | Medium (all) |

## 🐞 Failed Cases → Linked Bugs

| Test Case | Bug ID |
|---|---|
| TC-4, TC-5, TC-6 | HEAL-235 |
| TC-12 | HEAL-236 |
| TC-18, TC-19, TC-21 | HEAL-237 |
| TC-24 | HEAL-238 |

See `Bugs_Reports/` for full defect details.
