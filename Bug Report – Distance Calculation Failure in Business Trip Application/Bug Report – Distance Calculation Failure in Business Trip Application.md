# Bug Report – Distance Calculation Failure in Business Trip Application

## Overview

This repository contains a real-world bug report created during manual testing of a business trip management application.

The issue occurs when attempting to calculate the travel distance using an external railway service. Instead of displaying the route selection page, the external service returns an **Access Denied** page, preventing the business trip settlement process from continuing.

---

## Environment

| Property | Value |
|----------|-------|
| OS | Windows 11 |
| Browser | Google Chrome |
| Testing type | Manual Testing |
| Tools | Chrome DevTools (Network, Application) |

---

## Severity

**High**

The user cannot complete the business trip settlement process.

---

## Priority

High

---

## Preconditions

- User is authenticated.
- A business trip task is available.
- Required trip information is entered.

---

## Steps to Reproduce

1. Log into the application.
2. Open **Business Trip Settlement**.
3. Fill required trip information.
4. Click **Check distance**.
5. The application opens the external railway distance service.
6. Observe the result.

---

## Expected Result

The external service should open correctly and allow the user to calculate the travel distance.

The calculated distance should be returned to the application.

---

## Actual Result

The external service displays an **Access Denied** page.

The settlement process cannot be completed.

---

## Error Message

```
Access Denied

You don't have permission to access this resource on this server.
```

Application message:

```
A network connection problem occurred.
Please repeat the last action or refresh the page.
```

---

## Evidence

The repository contains screenshots documenting the complete scenario.

Screenshots:

```
├── 01_main_menu.png
├── 02_task_list.png
├── 03_click_check_distance.png
├── 04_network_connetion_occured.png
├── 05_access_denied_session_storage.png
├── 06_access_denied_local_storage
├── 07_browser_cookies.png
```

---

## Investigation

Chrome DevTools inspection showed:

- No JavaScript exceptions
- No failed API requests inside the application
- Session and Local Storage available
- Cookies correctly created
- External page returned **Access Denied**

The issue appears to originate from the external integration rather than the application itself.

---

## Root Cause (Hypothesis)

Possible causes include:

- External service authorization changes
- Reverse proxy / WAF restrictions
- Missing authentication token
- Integration endpoint changes

Further investigation would require backend logs and server-side access.

---

## Skills Demonstrated

- Manual Testing
- Bug Reporting
- Test Documentation
- Chrome DevTools
- Network Analysis
- Browser Storage Inspection
- Root Cause Analysis
