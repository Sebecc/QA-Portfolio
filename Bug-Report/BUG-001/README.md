# Startup Crash - Browser RPG Game "Flesh, Blood & Concrete"

## Summary
The game crashes immediately after launch and displays a JavaScript error message instead of loading the main menu.

## Environment
- Platform: PC
- Operating System: Windows 11
- Browser: Google Chrome
- Game Version: Latest available browser version
- Reproducibility: 5/5 attempts

## Steps to Reproduce
1. Open the game page in the browser.
2. Click the "Play" button.
3. Wait for the game to load.

## Expected Result
The game should launch successfully and display the main menu.

## Actual Result
The game fails to initialize and displays the following error message:
TypeError: Cannot read properties of undefined (reading 'blendModes')

## Severity
Critical

## Priority
High

## Additional Information
The stack trace suggests that the issue occurs during graphics renderer initialization, possibly due to a rendering or plugin compatibility issue.

## Screenshot
See `startup_crash.png`.
