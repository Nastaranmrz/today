# Test Plan & Results | To do list

This document records repeatable manual checks for the app. It complements automated checks; it does not replace testing on real devices or assistive technology.

**Live app:** [nastaranmrz.github.io/today](https://nastaranmrz.github.io/today/)  
**Latest test run:** October 23, 2026  
**Test environment:** Desktop browser in the Codex in-app browser; exact browser version and viewport were not exposed  
**End state:** Four sample tasks, one completed; temporary test data removed

## Status key

| Status | Meaning |
|---|---|
| PASS | Observed behavior met the success criteria |
| FAIL | Observed behavior did not meet the criteria; record an issue |
| PARTIAL | Only part of the scenario was verified |
| BLOCKED | Could not run because the required device or capability was unavailable |
| NOT RUN | Has not been tested |

## Before you start

1. Record the app URL, date, operating system, browser, and viewport.
2. Use a unique task title with the `QA-` prefix so test data is easy to find.
3. Remove temporary tasks and restore the sample task state after testing.
4. Do not clear browser storage as part of routine checks; this can erase the user's saved tasks.
5. For each scenario, record the actual result, duration, errors, and any useful screenshot.

## App loading and daily list

| ID | User goal | Steps | Success criteria | Latest result |
|---|---|---|---|---|
| APP-01 | View today's tasks | Open the app and inspect the date, task cards, and completion count. | The list renders and the completion count matches the visible completed tasks. | **PASS** — about 1 second; 4 sample tasks, 1 completed |

## Creating and managing tasks

| ID | User goal | Steps | Success criteria | Latest result |
|---|---|---|---|---|
| TASK-01 | Prevent an empty task | Open the new-task sheet and leave the title blank. | Add remains disabled and no empty task is created. | **PASS** |
| TASK-02 | Create a task | Create a task titled `QA-Test task` with a short description. | The sheet closes and the task appears with the entered title and description. | **PASS** — about 2.1 seconds; test task removed |
| TASK-03 | Edit a task | Edit a temporary task and change its title or description. | The updated value appears and replaces the old value. | **PASS** — about 1.4 seconds; test task removed |
| TASK-04 | Toggle completion | Toggle one task's checkbox on and off. | Only that task changes; its appearance and the completion count update. | **PASS** — only the selected task changed; count updated |
| TASK-05 | Delete a task | Delete a temporary task and inspect the list. | The task disappears; other tasks and their states remain unchanged. | **PASS** — delete action was also activated with the keyboard |
| TASK-06 | Cancel without saving | Open the add or edit sheet, enter a value, then choose Cancel. | The sheet closes and the unsaved value is not retained. | **PASS** — about 1 second |

## Search and filters

| ID | User goal | Steps | Success criteria | Latest result |
|---|---|---|---|---|
| FIND-01 | Find a task | Search for part of a sample task's title. | Only matching tasks are shown. | **PASS** — about 0.7 seconds |
| FIND-02 | Search for a missing task | Search for a string that does not exist. | A clear no-results state appears without a broken or ambiguous blank screen. | **PASS** |
| FIND-03 | Filter completed tasks | Select Completed, then select All. | Each filter shows the correct tasks; All restores the full daily list. | **PASS** — 4 tasks total, 1 completed |

## Dates, recurrence, and time

| ID | User goal | Steps | Success criteria | Latest result |
|---|---|---|---|---|
| DATE-01 | Schedule a task for tomorrow | Create a temporary task, choose tomorrow, save, then revisit today's list. | The task is associated with tomorrow and today's list is correct when revisited. | **PASS** — about 1.1 seconds; test task removed |
| DATE-02 | Repeat a task daily | Enable Every day while creating a temporary task. | The saved task shows the daily recurrence setting. | **PASS** — checked with a temporary task |
| DATE-03 | Navigate calendar months | Open the date picker, move to the next month, then back to the previous month. | The month title changes in both directions and returning restores the original month. | **PASS** — observed Aban 1405 → Azar 1405 → Aban 1405 |
| TIME-01 | Set a single time | Choose Single time and set a temporary task to 13:30. | The selected time is accepted and appears on the task. | **PASS** — checked with a temporary task |
| TIME-02 | Set a valid time range | Choose Time range and set a start and a later end time; save the task. | Both times are accepted and the saved task displays the range. | **PARTIAL** — start/end controls appeared; a saved valid range was not confirmed |
| TIME-03 | Reject an invalid time range | Set the end time earlier than the start time. | Saving is blocked and a clear validation message appears. | **PASS** — validation message appeared in under 1 second |

## Navigation and panels

| ID | User goal | Steps | Success criteria | Latest result |
|---|---|---|---|---|
| NAV-01 | Open and dismiss the menu/account panel | Open the menu, open the account panel, then cancel or close it. | The expected panel opens and closes without saving unintended changes. | **PASS** |
| NAV-02 | Check notifications | Open and close the notifications panel. | The panel opens, its empty state is understandable, and it can be dismissed. | **PASS** |
| NAV-03 | Navigate to Calendar and back Home | Select Calendar in the bottom navigation, then return Home. | The destination opens and Home can be reached again. | **PASS** — navigation works; Calendar content was still a placeholder during the run |

## Remaining checks and known limits

| ID | Check | Success criteria | Status / limitation |
|---|---|---|---|
| MOB-01 | On a phone, open the keyboard in the Add Task sheet and scroll the form. | The active field and Add/Cancel buttons remain visible and usable above the keyboard. | **BLOCKED** — no phone or mobile viewport control was available in this test environment; re-run on a real phone after the CSS update. |
| MOB-02 | Repeat the keyboard check in the account edit sheet. | Save and Cancel remain visible and usable above the keyboard. | **BLOCKED** — requires a real phone or mobile browser test. |
| MOB-03 | Open the numeric keyboard in both Single time and Time range sheets. | Inputs and confirmation/cancel buttons remain visible and usable. | **BLOCKED** — requires a real phone or mobile browser test. |
| DATA-01 | Create a temporary task, load the same app in a fresh tab, and check the task. | The task remains available after a new page load without clearing storage. | **PASS** — task appeared in a fresh tab; temporary task was deleted afterward. A browser-level hard refresh was not available. |
| A11Y-01 | Navigate the main controls using Tab and verify names with a screen reader. | Focus order is logical and controls have understandable accessible names. | **PARTIAL** — Tab moved focus through controls, but the complete focus order and screen-reader output were not verified. |
| OFFLINE-01 | Load the app, disconnect the network, and reopen it. | Record whether the app supports the expected offline behavior. | **BLOCKED** — this browser did not expose network-offline controls; offline support remains unverified. |
| ERR-01 | Run the main flows and inspect the browser console. | No new JavaScript errors appear. | **PASS** in the previous run; no console errors were observed. |

## Reusable run record

Copy this block for each new test run:

```text
Date and time:
App URL / version / commit:
Device and operating system:
Browser and version:
Viewport:
Scenario ID:
Duration:
Result: PASS / FAIL / PARTIAL / BLOCKED / NOT RUN
Observed result:
Console or validation errors:
Screenshot or issue link:
Test data cleanup:
```

## Latest run notes

The main scenarios were run against the published GitHub Pages app on October 23, 2026, in a desktop in-app browser. The month navigation and task persistence in a fresh tab were checked during the follow-up run. No temporary QA task was left behind. The browser did not provide a mobile viewport, a screen reader, or network toggling, so mobile keyboard behavior, full accessibility, and offline support remain unverified.


