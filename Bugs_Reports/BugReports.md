# Bug Reports — Healthcare Clinic Booking Platform

## 📋 Overview
This folder contains all defects discovered during manual testing of the **Healthcare Clinic Booking Platform**, covering the Patient Authentication and Appointment Dashboard & Cancellation modules.

**Tester:** Omar Ahmed

## 📁 Folder Contents

| File | Description |
|---|---|
| `BugReports.md` | Bug reports in Markdown format |
| `Healthcare_Booking_Bugs.pdf` | Bug reports in PDF format |
| `Screenshot 2026-09-11 181051.png` | Evidence screenshot |
| `Screenshot 2026-09-11 181341.png` | Evidence screenshot |
| `image-20260911-150303.png` | Evidence screenshot |
| `image-20260911-154501.png` | Evidence screenshot |
| `20260911-1616-32.8435281.mp4` | Screen recording demonstrating a defect |

## 🐞 Bug Summary

| Bug ID | Module | Severity | Summary |
|---|---|---|---|
| HEAL-236 | Authentication | High | Passwords stored as plain text in localStorage (`carenest_users`) |
| HEAL-238 | Post-Booking Lifecycle | High | Cancelled slot doesn't revert to "Available" — blocks re-booking |
| HEAL-237 | Post-Booking Lifecycle | High | Cancel button stays active for appointments within 24 hours |
| HEAL-235 | Authentication | Medium | Missing client-side required-field validation on Login form |

## 🔍 Bug Details

### HEAL-238 — Cancelled slot does not revert to "Available"
- **Steps:** Book a slot → cancel it from My Bookings → try to book the same slot again → confirm.
- **Expected:** Slot reverts to "Available" and can be rebooked by any patient.
- **Actual:** Slot stays "Booked"; error shown: *"This slot has just been booked. Please choose another time."*
- **Linked Test Case:** HEAL-227

### HEAL-237 — Cancel button active within 24h (missing restriction & tooltip)
- **Steps:** Book an appointment within the next 24 hours → open My Bookings → inspect the Cancel button.
- **Expected:** Button disabled with tooltip *"Cancellations are only allowed up to 24 hours before the appointment."*
- **Actual:** Button remains clickable, allows cancellation with no tooltip.
- **Linked Test Cases:** HEAL-221, HEAL-222, HEAL-224

### HEAL-236 — Passwords exposed as plain text in localStorage
- **Steps:** Log in → open DevTools → Application → Local Storage → inspect `carenest_users`.
- **Expected:** Passwords never stored in plain text (hashed or handled via secure session tokens).
- **Actual:** Password field exposed unencrypted, e.g. `"password":"patient123"`.
- **Linked Test Case:** HEAL-85

### HEAL-235 — Missing required-field validation on Login form
- **Steps:** Submit the login form with Email/Phone empty, Password empty, or both empty.
- **Expected:** Each empty field flagged inline, submission blocked client-side.
- **Actual:** No inline validation; generic error *"Invalid email/phone or password."* shown instead.
- **Linked Test Cases:** HEAL-76, HEAL-77, HEAL-78

## 📊 Severity Breakdown

| Severity | Count |
|---|---|
| High | 3 |
| Medium | 1 |

## 📌 Status
All bugs reported to the development team, pending fixes and retesting.
