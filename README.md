# Automated-Instagram-Comment-Deletion-Tool
Instagram Comment Bulk-Delete Script (Visible-Only Version)

This script automates the deletion of visible Instagram comments from the Your Activity → Interactions → Comments page. It selects up to a configurable number of comments at a time (default: 15), clicks the bottom Delete button, confirms the popup, and waits for Instagram to refresh the list.


Important Disclaimer

Before using this script:

Read the entire script first.

Understand exactly what it does.
Running any automation in your browser can cause unintended changes.

You run this script at your own risk.
This script interacts with your real Instagram account.

I am not responsible for account issues, rate limits, login challenges, or accidental deletion of comments.

This script does not bypass Instagram permissions, limits, or security.

If you do not understand what the script does, do not run it.

Browser DevTools Warning

When you open the browser’s Developer Console, you may see warnings such as:

“Do not paste code you do not understand into this console. Attackers may trick you into doing something harmful…”

These are normal and appear in all modern browsers to protect users from scams.
This is expected.

You should only continue if you understand what the script does and why you’re using it.

Features

Deletes ONLY comments that are currently visible on the screen

Selects up to 15 visible comments per batch (customizable)

Clicks the bottom Delete button automatically

Confirms the Instagram popup delete prompt

Waits for Instagram to reload the list before continuing

Can be stopped at any time with a single command (stopAuto = True)

How to Open the Developer Console
OperaGX

Windows: CtRL + Shift + I

Mac: Cmd + Option I

Google Chrome

Windows: Ctrl + Shift + J

Mac: Cmd + Option + J

Or: Right-click → Inspect → Console tab

Firefox

Windows: Ctrl + Shift + K

Mac: Cmd + Option + K

Or: Right-click → Inspect → Console tab

Microsoft Edge

Windows: Ctrl + Shift + J

Right-click → Inspect → Console tab

Safari (Mac)

Enable DevTools: Safari → Preferences → Advanced → ✔ “Show Develop menu”

Open Console: Cmd + Option + C

How to Use the Script
1. Log into Instagram

Go to:

instagram.com/your_activity/interactions/comments

2. Make sure comments are visible

Zoom out on the page until about 15 comments are visible (CRTL + MwheelDown) 

3. Open the Dev Console

(See instructions above)

4. Paste the script into the console

Copy the entire script and paste it into the console.

5. Press Enter

The script will begin:

Clicking Select

Selecting up to 15 visible comments

Clicking Delete

Confirming the popup

Pausing until IG refreshes

6. When it stops

You will see:

No visible comments to process; stopping.


At that point:

Increase Wait_After_Delete time and rerun code

Refresh the page if you recieve an Instagram error

Rerun code

7. To stop the script at any time

Run:

stopAuto = true;

Configuration

Inside the script you can safely edit:

Batch size (how many comments per cycle):
const BATCH_SIZE = 15;

Delay after each mass delete:
const WAIT_AFTER_DELETE = 8500; // milliseconds
const MAX_POPUP_WAIT = 5000;        // ms
const POPUP_POLL_INTERVAL = 200;    // ms between popup checks
const WAIT_AFTER_DELETE = 12000;     // ms wait after delete (with or without popup)
const TIME_AFTER_SELECT = 400;      // ms after clicking "Select"
// (scroll-related timing removed)

Safety Notes

The script interacts only with the public Instagram UI, just like a human user.

It does not hack, bypass restrictions, or use private APIs.

It only selects and deletes comments you can already see.

If Instagram changes its layout, selectors may break.

Final Notes

This tool is intended for people who need to clean up large numbers of old comments and don’t want to delete them one at a time manually.

You are responsible for what gets deleted — double-check before running the script.

