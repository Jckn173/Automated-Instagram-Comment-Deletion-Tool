<?xml version="1.0" encoding="UTF-8"?>
<README>

  <!-- ========================================================= -->
  <!-- Automated-Instagram-Comment-Deletion-Tool                -->
  <!-- ========================================================= -->

  <section title="Automated-Instagram-Comment-Deletion-Tool">
    <header>Automated-Instagram-Comment-Deletion-Tool</header>

    <subheader>Instagram Comment Bulk-Delete Script (Visible-Only Version)</subheader>

    <paragraph>
      This script automates the deletion of visible Instagram comments from the 
      <i>Your Activity → Interactions → Comments</i> page. It selects up to a configurable 
      number of comments at a time (default: 15), clicks the bottom Delete button, 
      confirms the popup, and waits for Instagram to refresh the list.
    </paragraph>
  </section>


  <!-- ========================================================= -->
  <!-- Important Disclaimer                                      -->
  <!-- ========================================================= -->

  <section title="Important Disclaimer">
    <header>Important Disclaimer</header>

    <paragraph>Before using this script:</paragraph>

    <list>
      <item><b>Read the entire script first.</b></item>
      <item><b>Understand exactly what it does.</b></item>
      <item>Running any automation in your browser can cause unintended changes.</item>
      <item>You run this script <b>at your own risk</b>.</item>
      <item>This script interacts with your real Instagram account.</item>
      <item>I am not responsible for account issues, rate limits, login challenges, or accidental deletion of comments.</item>
      <item>This script does not bypass Instagram permissions, limits, or security.</item>
    </list>

    <paragraph>
      <u>If you do not understand what the script does, do not run it.</u>
    </paragraph>
  </section>


  <!-- ========================================================= -->
  <!-- Browser DevTools Warning                                  -->
  <!-- ========================================================= -->

  <section title="Browser DevTools Warning">
    <header>Browser DevTools Warning</header>

    <paragraph>
      When you open the browser’s Developer Console, you may see warnings such as:
    </paragraph>

    <quote>
      "Do not paste code you do not understand into this console. Attackers may 
      trick you into doing something harmful…"
    </quote>

    <paragraph>
      These are normal and appear in all modern browsers to protect users from scams. 
      This is expected. You should only continue if you understand what the script 
      does and why you’re using it.
    </paragraph>
  </section>


  <!-- ========================================================= -->
  <!-- Features                                                   -->
  <!-- ========================================================= -->

  <section title="Features">
    <header>Features</header>

    <list>
      <item>Deletes ONLY comments that are currently visible on the screen</item>
      <item>Selects up to 15 visible comments per batch (customizable)</item>
      <item>Clicks the bottom Delete button automatically</item>
      <item>Confirms the Instagram popup delete prompt</item>
      <item>Waits for Instagram to reload the list before continuing</item>
      <item>Can be stopped at any time with a single command (<code>stopAuto = true</code>)</item>
    </list>
  </section>


  <!-- ========================================================= -->
  <!-- How to Open the Developer Console                         -->
  <!-- ========================================================= -->

  <section title="How to Open the Developer Console">
    <header>How to Open the Developer Console</header>

    <subheader>OperaGX</subheader>
    <list>
      <item>Windows: <b>Ctrl + Shift + I</b></item>
      <item>Mac: <b>Cmd + Option + I</b></item>
    </list>

    <subheader>Google Chrome</subheader>
    <list>
      <item>Windows: <b>Ctrl + Shift + J</b></item>
      <item>Mac: <b>Cmd + Option + J</b></item>
      <item>Right-click → Inspect → Console tab</item>
    </list>

    <subheader>Firefox</subheader>
    <list>
      <item>Windows: <b>Ctrl + Shift + K</b></item>
      <item>Mac: <b>Cmd + Option + K</b></item>
      <item>Right-click → Inspect → Console tab</item>
    </list>

    <subheader>Microsoft Edge</subheader>
    <list>
      <item>Windows: <b>Ctrl + Shift + J</b></item>
      <item>Right-click → Inspect → Console tab</item>
    </list>

    <subheader>Safari (Mac)</subheader>
    <list>
      <item>Enable DevTools: Safari → Preferences → Advanced → “Show Develop menu”</item>
      <item>Open Console: <b>Cmd + Option + C</b></item>
    </list>
  </section>


  <!-- ========================================================= -->
  <!-- How to Use the Script                                     -->
  <!-- ========================================================= -->

  <section title="How to Use the Script">
    <header>How to Use the Script</header>

    <subheader>1. Log into Instagram</subheader>
    <paragraph>Go to:</paragraph>
    <code>instagram.com/your_activity/interactions/comments</code>

    <subheader>2. Make sure comments are visible</subheader>
    <paragraph>
      Zoom out on the page until about 15 comments are visible (CTRL + Mouse Wheel Down).
    </paragraph>

    <subheader>3. Open the Dev Console</subheader>
    <paragraph>(See instructions above)</paragraph>

    <subheader>4. Paste the script into the console</subheader>
    <paragraph>Copy the entire script and paste it into the console.</paragraph>

    <subheader>5. Press Enter</subheader>
    <paragraph>The script will begin:</paragraph>
    <list>
      <item>Clicking Select</item>
      <item>Selecting up to 15 visible comments</item>
      <item>Clicking Delete</item>
      <item>Confirming the popup</item>
      <item>Pausing until IG refreshes</item>
    </list>

    <subheader>6. When it stops</subheader>
    <paragraph>You will see:</paragraph>
    <quote>No visible comments to process; stopping.</quote>

    <paragraph>At that point:</paragraph>
    <list>
      <item>Increase <i>WAIT_AFTER_DELETE</i> time and rerun the code</item>
      <item>Refresh the page if you receive an Instagram error</item>
      <item>Rerun the script</item>
    </list>

    <subheader>7. To stop the script at any time</subheader>
    <code>stopAuto = true;</code>
  </section>


  <!-- ========================================================= -->
  <!-- Configuration                                              -->
  <!-- ========================================================= -->

  <section title="Configuration">
    <header>Configuration</header>

    <paragraph>Inside the script you can safely edit:</paragraph>

    <subheader>Batch size (how many comments per cycle)</subheader>
    <code>const BATCH_SIZE = 15;</code>

    <subheader>Delay after each mass delete</subheader>
    <code>
      const WAIT_AFTER_DELETE = 8500; // milliseconds
      const MAX_POPUP_WAIT = 5000;    // ms
      const POPUP_POLL_INTERVAL = 200;// ms between popup checks
      const WAIT_AFTER_DELETE = 12000;// ms wait after delete
      const TIME_AFTER_SELECT = 400;  // ms after clicking "Select"
    </code>
  </section>


  <!-- ========================================================= -->
  <!-- Safety Notes                                               -->
  <!-- ========================================================= -->

  <section title="Safety Notes">
    <header>Safety Notes</header>

    <list>
      <item>The script interacts only with the public Instagram UI, just like a human user.</item>
      <item>It does not hack, bypass restrictions, or use private APIs.</item>
      <item>It only selects and deletes comments you can already see.</item>
      <item>If Instagram changes its layout, selectors may break.</item>
    </list>
  </section>


  <!-- ========================================================= -->
  <!-- Final Notes                                               -->
  <!-- ========================================================= -->

  <section title="Final Notes">
    <header>Final Notes</header>

    <paragraph>
      This tool is intended for people who need to clean up large numbers of old comments 
      and do not want to delete them one at a time manually.
    </paragraph>

    <paragraph>
      You are responsible for what gets deleted — always double-check before running the script.
    </paragraph>
  </section>

</README>
