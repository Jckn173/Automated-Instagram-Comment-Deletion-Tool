// ==== TIMING (tweak if needed) ====
// Total time to wait for confirmation popup to appear after bottom Delete
const MAX_POPUP_WAIT = 5000;        // ms
const POPUP_POLL_INTERVAL = 200;    // ms between popup checks
const WAIT_AFTER_DELETE = 15000;     // ms wait after delete (with or without popup)
const TIME_AFTER_SELECT = 400;      // ms after clicking "Select"
// (scroll-related timing removed)

// How many comments to select per loop
const BATCH_SIZE = 15;
// Small delay between selecting each comment in the batch
const TIME_BETWEEN_SELECTIONS = 150; // ms

// Global stop flag
window.stopAuto = false;

// Circle icon to select a comment
const CIRCLE_SELECTOR =
  'div[data-bloks-name="ig.components.Icon"][style*="circle__outline__24-4x.png"]';

// Blue "Select" text
const SELECT_TOGGLE_SELECTOR =
  'span[data-bloks-name="bk.components.Text"]';

// Any "Delete" text span
const TEXTSPAN_SELECTOR =
  'span[data-bloks-name="bk.components.TextSpan"]';

function delay(ms) {
  return new Promise(res => setTimeout(res, ms));
}

function isVisible(el) {
  const rect = el.getBoundingClientRect();
  return (
    rect.width > 0 &&
    rect.height > 0 &&
    rect.top < window.innerHeight &&
    rect.bottom > 0
  );
}

// Click the blue "Select" text if visible
async function clickSelectIfVisible() {
  const spans = Array.from(document.querySelectorAll(SELECT_TOGGLE_SELECTOR))
    .filter(el => el.textContent.trim() === "Select");

  for (const span of spans) {
    if (!isVisible(span)) continue;
    try {
      span.click();
      console.log("▶ Clicked Select");
      await delay(TIME_AFTER_SELECT);
      return true;
    } catch (e) {
      console.log("⚠ Failed to click Select:", e);
    }
  }
  return false;
}

// Get up to BATCH_SIZE visible selection circles
function getVisibleCircleBatch() {
  const circles = Array.from(document.querySelectorAll(CIRCLE_SELECTOR))
    .filter(el => isVisible(el));

  return circles.slice(0, BATCH_SIZE);
}

// Count visible circles (not used for scrolling anymore, but can be useful for logs)
function countVisibleCircles() {
  return Array.from(document.querySelectorAll(CIRCLE_SELECTOR))
    .filter(el => isVisible(el)).length;
}

// Find the bottom "Delete" button (bulk delete, not popup)
function getBulkDeleteButton() {
  // 1) Find all TextSpan "Delete" labels
  const deleteLabels = Array.from(
    document.querySelectorAll(TEXTSPAN_SELECTOR)
  ).filter(el => el.textContent.trim() === "Delete");

  for (const label of deleteLabels) {
    // Skip the popup delete – its label is inside ._a9-v
    if (label.closest('div._a9-v')) continue;

    if (!isVisible(label)) continue;

    // 2) Find a clickable ancestor: button, role="button", or something with tabindex
    let clickable =
      label.closest('button, [role="button"], [tabindex]') ||
      label.parentElement;

    if (!clickable) continue;
    if (!isVisible(clickable)) continue;

    // Bias to bottom area of the viewport (bulk bar)
    const rect = clickable.getBoundingClientRect();
    if (rect.top < window.innerHeight * 0.4) continue;

    return clickable;
  }

  return null;
}

// Popup "Delete" button
function getPopupDeleteButton() {
  const buttons = document.querySelectorAll('div._a9-v button');
  for (const btn of buttons) {
    const txt = btn.innerText && btn.innerText.trim();
    if (txt && txt.startsWith("Delete")) {
      return btn;
    }
  }
  return null;
}

// Wait (polling) for popup Delete button to appear
async function waitForPopupDelete() {
  const start = Date.now();
  while (Date.now() - start < MAX_POPUP_WAIT) {
    const btn = getPopupDeleteButton();
    if (btn) return btn;
    await delay(POPUP_POLL_INTERVAL);
  }
  return null;
}

async function deleteLoop() {
  console.log("▶ Starting loop. Select → up to 15 *visible* comments → bottom Delete → (optional popup Delete) → wait.");

  while (!window.stopAuto) {
    // Step 1: click Select if present
    await clickSelectIfVisible();

    // Step 2: get batch of up to BATCH_SIZE visible circles
    let batch = getVisibleCircleBatch();
    if (batch.length === 0) {
      console.log("✔ No visible comments to process; stopping.");
      break;
    }

    console.log(`✅ Selecting ${batch.length} comment(s) in this batch.`);

    // Step 2b: click each circle in the batch
    for (const circle of batch) {
      try {
        circle.click();
        await delay(TIME_BETWEEN_SELECTIONS);
      } catch (e) {
        console.log("⚠ Failed to click selection circle:", e);
      }
    }

    // Step 3: click bottom Delete button
    const bulkDeleteBtn = getBulkDeleteButton();
    if (!bulkDeleteBtn) {
      console.log("⚠ Bulk Delete button not found; stopping.");
      break;
    }

    try {
      bulkDeleteBtn.click();
      console.log("▶ Clicked bottom Delete button.");
    } catch (e) {
      console.log("⚠ Failed to click bottom Delete:", e);
      break;
    }

    // Step 4: WAIT for popup Delete to exist (poll) – but it's OPTIONAL
    const popupDelete = await waitForPopupDelete();
    if (popupDelete) {
      try {
        popupDelete.click();
        console.log("🗑 Confirmed Delete in popup.");
      } catch (e) {
        console.log("⚠ Failed to click popup Delete (ignoring, will continue).", e);
      }
    } else {
      console.log("ℹ No popup Delete found – assuming delete happened without confirmation.");
    }

    // Step 5: wait for IG to update list
    console.log(`⏳ Waiting ${WAIT_AFTER_DELETE / 1000}s before next batch...`);
    await delay(WAIT_AFTER_DELETE);

    const remainingVisible = countVisibleCircles();
    console.log(`👀 Visible circles after delete: ${remainingVisible}`);

    if (window.stopAuto) {
      console.log("⛔ Stopped manually after delete.");
      break;
    }
  }

  console.log("⏹ Loop finished or stopped. To run again: stopAuto = false; deleteLoop();");
}

// Start
deleteLoop();
