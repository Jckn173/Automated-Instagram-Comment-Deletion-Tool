Automated-Instagram-Comment-Deletion-Tool
Instagram Comment Bulk-Delete Script (Visible-Only Version)

This script automates the deletion of visible Instagram comments from the
Your Activity → Interactions → Comments page.
It selects up to a configurable number of comments at a time (default: 15), clicks the bottom Delete button, confirms the popup, and waits for Instagram to refresh the list.

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

These warnings appear in all modern browsers.
They are normal and expected.

You should only continue if you understand what the script does and why you're using it.

Features

Deletes only comments visible on the screen

Selects up to 15 visible comments per batch

Automatically clicks the bottom Delete button

Confirms the Instagram popup delete prompt

Waits for Instagram to refresh the comment list

Can be stopped at any time with:
stopAuto = true;

How to Open the Developer Console
Opera GX

Windows: Ctrl + Shift + I

Mac: Cmd + Option + I

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

Or: Right-click → Inspect → Console tab

Safari (Mac)

Enable DevTools: Safari → Preferences → Advanced → enable Show Develop Menu

Open console: Cmd + Option + C

How to Use the Script
1. Log into Instagram

Go to:

instagram.com/your_activity/interactions/comments

2. Make sure comments are visible

Zoom out until ~15 comments are visible.
(Ctrl + Mouse Wheel Down)

3. Open the Dev Console

(Use the instructions above.)

4. Paste the script into the console

Copy the entire script and paste it.

5. Press Enter

The script will begin:

Clicking Select

Selecting up to 15 visible comments

Clicking Delete

Confirming the delete popup

Waiting for Instagram to refresh

6. When it stops

You may see:

No visible comments to process; stopping.


At that point:

Increase WAIT_AFTER_DELETE time and rerun the script

Refresh the page if Instagram shows an error

Run the script again

7. To stop the script

Run:

stopAuto = true;

Configuration
Batch size
const BATCH_SIZE = 15;

Timing parameters
const WAIT_AFTER_DELETE = 8500;     // milliseconds
const MAX_POPUP_WAIT = 5000;        // ms
const POPUP_POLL_INTERVAL = 200;    // ms
const WAIT_AFTER_DELETE = 12000;    // ms (longer=safer)
const TIME_AFTER_SELECT = 400;      // ms

Safety Notes

Script interacts only with the public Instagram UI

Does not hack or bypass restrictions

Only deletes comments that are already visible

Selectors may break if Instagram changes the layout

Final Notes

This tool is for users who need to delete large numbers of old comments without doing it manually.

You are responsible for what gets deleted — always double-check before running the script.
