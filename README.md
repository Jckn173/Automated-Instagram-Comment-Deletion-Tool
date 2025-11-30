<h1>Automated-Instagram-Comment-Deletion-Tool</h1>
<h2>Instagram Comment Bulk-Delete Script </h2>
<hr>

<p>
This script automates the deletion of visible Instagram comments from the Your Activity → Interactions → Comments page. It selects up to a configurable number of comments at a time (default: 15), clicks the bottom Delete button, confirms the popup, and waits for Instagram to refresh the list. Then repeats, it does about 15 at a time because Instagram seems to not like it if you do too much stuff too quickly. 
</p>

<h2>Important Disclaimer</h2>
<hr>

<p>Before using this script:</p>

<ul>
  <li>Read the entire script first.</li>
  <li>Understand exactly what it does.</li>
  <li>Running any automation in your browser can cause unintended changes.</li>
  <li>If you cannot read and understand browser-side JavaScript or know someone you trust who does, do not run this script</li>
  <li>You run this script at your own risk.</li>
  <li>This script interacts with your real Instagram account.</li>
  <li>I am not responsible for account issues, rate limits, login challenges, or accidental deletion of comments.</li>
  <li>This script does not bypass Instagram permissions, limits, or security.</li>
</ul>

<p><b>If you do not understand what the script does, do not run it.</b></p>

<h2>Browser DevTools Warning</h2>
<hr>

<p>When you open the browser’s Developer Console, you may see warnings such as:</p>

<p><i>“Do not paste code you do not understand into this console. Attackers may trick you into doing something harmful…”</i></p>

<p>
These are normal and appear in all modern browsers to protect users from scams. This is expected.
</p>

<p>
You should only continue if you understand what the script does and why you’re using it.
</p>

<h2>Features</h2>
<hr>

<ul>
  <li>Deletes ONLY comments that are currently visible on the screen</li>
  <li>Selects up to 15 visible comments per batch (customizable)</li>
  <li>Clicks the bottom Delete button automatically</li>
  <li>Confirms the Instagram popup delete prompt</li>
  <li>Waits for Instagram to reload the list before continuing</li>
  <li>Can be stopped at any time with a single command (stopAuto = True)</li>
</ul>

<h2>How to Open the Developer Console</h2>
<hr>

<h3>OperaGX</h3>
<ul>
  <li>Windows: CtRL + Shift + I</li>
  <li>Mac: Cmd + Option I</li>
</ul>

<h3>Google Chrome</h3>
<ul>
  <li>Windows: Ctrl + Shift + J</li>
  <li>Mac: Cmd + Option + J</li>
  <li>Or: Right-click → Inspect → Console tab</li>
</ul>

<h3>Firefox</h3>
<ul>
  <li>Windows: Ctrl + Shift + K</li>
  <li>Mac: Cmd + Option + K</li>
  <li>Or: Right-click → Inspect → Console tab</li>
</ul>

<h3>Microsoft Edge</h3>
<ul>
  <li>Windows: Ctrl + Shift + J</li>
  <li>Right-click → Inspect → Console tab</li>
</ul>

<h3>Safari (Mac)</h3>
<ul>
  <li>Enable DevTools: Safari → Preferences → Advanced → ✔ “Show Develop menu”</li>
  <li>Open Console: Cmd + Option + C</li>
</ul>

<h2>How to Use the Script</h2>
<hr>

<h3>1. Log into Instagram</h3>
<p>Go to:</p>
<pre>instagram.com/your_activity/interactions/comments</pre>

<h3>2. Make sure comments are visible</h3>
<p>Zoom out on the page until about 15 comments are visible (CRTL + MwheelDown)</p>

<h3>3. Open the Dev Console</h3>
<p>(See instructions above)</p>

<h3>4. Paste the script into the console</h3>
<p>Copy the entire script and paste it into the console.</p>

<h3>5. Press Enter</h3>
<p>The script will begin:</p>
<ul>
  <li>Clicking Select</li>
  <li>Selecting up to 15 visible comments</li>
  <li>Clicking Delete</li>
  <li>Confirming the popup</li>
  <li>Pausing until IG refreshes</li>
</ul>

<h3>6. When it stops</h3>
<p>You will see:</p>
<pre>No visible comments to process; stopping.</pre>

<p>At that point:</p>
<ul>
  <li>Increase Wait_After_Delete time and rerun code</li>
  <li>Refresh the page if you recieve an Instagram error</li>
  <li>Rerun code</li>
  <li>You've deleted all comments, you're done</li>
</ul>

<h3>7. To stop the script at any time</h3>
<p>Run:</p>
<pre>stopAuto = true;</pre>

<h2>Configuration</h2>
<hr>

<p>Inside the script you can safely edit:</p>

<p><b>Batch size (how many comments per cycle):</b></p>
<pre>const BATCH_SIZE = 15;</pre>

<p><b>Delay after each mass delete:</b></p>
<pre>
const WAIT_AFTER_DELETE = 12000; // milliseconds (reccomend 12s or above for average internet speeds, test for yourself though)
const MAX_POPUP_WAIT = 5000; // ms
const POPUP_POLL_INTERVAL = 200; // ms between popup checks
const TIME_AFTER_SELECT = 400; // ms after clicking "Select"
</pre>

<h2>Safety Notes</h2>
<hr>

<ul>
  <li>The script interacts only with the public Instagram UI, just like a human user.</li>
  <li>It does not hack, bypass restrictions, or use private APIs.</li>
  <li>It only selects and deletes comments you can already see.</li>
  <li>If Instagram changes its layout, selectors may break.</li>
</ul>

<h2>Final Notes</h2>
<hr>

<p>
This tool is intended for people who need to clean up large numbers of old comments and don’t want to delete them one at a time manually.
</p>

<p>
You are responsible for what gets deleted — double-check before running the script.
</p>
