---
name: antislop-human
description: "Human and accessibility skill for antislop. Contrast, keyboard, focus, and states for real people. Includes the contrast checker."
allowed-tools: Bash(python *) Bash(python3 *) Read Write Edit Glob Grep
---
# antislop-human
Part of the antislop system. Read with `antislop.md` (core). Deep-dives the human concern: the UI must stay usable by people with different eyes, hands, and setups. Contrast, keyboard, focus, states, and the mobile details that exclude people.

## How to use
- Load with `antislop.md` whenever the task builds or edits UI. Core holds the mechanism (purpose test, three tiers, Delivery Gate); this skill holds the human-side depth: the parts of a UI that exclude people with different eyes, hands, and setups.
- Entry shape: **Tell** (pattern), **Why** (who it excludes and why it reads as unfinished), **Fix** (what to do), governing core rule cited R-XX.
- Accessibility is not a checklist of extras bolted on at the end. It's part of the core promise that "the UI holds up" (C-4). The core Delivery Gate remains the gate; the Human Skill Checklist at the end is the supplement.
- The contrast checker (formula + reference table + script) lives here. Use it for every color pairing you can't verify by eye.
- Keeps only the mobile details that exclude people: zooming, and the on-screen keyboard.

## Color & contrast

Low-contrast text. Tell: light grey text on white or near-white, thin body text, muted labels chosen to look "elegant" but hard to read. Why: excludes low-vision users and everyone in bright light; a visual choice made without checking the standard, exactly the default this filter catches. Fix: meet WCAG AA minimums (R-25): 4.5:1 normal text, 3:1 large text (18px+). Compute the ratio, don't eyeball it.

Text over a photo or gradient. Tell: white text directly over an image or gradient light in some areas, checked at one bright spot only. Why: contrast is local. Where the image is light, text drops below 4.5:1 even if the hero "looks" fine. R-25 requires testing the whole area the text passes over, not one point. Fix: add a scrim or solid color block behind the text, then verify the worst spot, not the best. Any part of the text area fails -> the treatment fails.

The grey-on-grey hallucination. Tell: "dark grey on black" or "light grey on white" claimed to pass AA without computation. Why: the most common accessibility hallucination. The eye overestimates contrast on grey pairs, and agents repeat the claim because it sounds plausible. #555555 on black is 2.8:1. It fails. Fix: never assert a pairing passes. Run the contrast checker (below) or apply the formula. Neither possible -> use the reference table.

Non-text contrast. Tell: interactive components (buttons, icons, input borders, focus indicators, chart segments) distinguished from their background by less than 3:1. Why: non-text UI carries information by shape and edge; when the edge is a hair of tint, low-vision users can't find the control. Same bar for hover and selected. Fix: every component boundary and status indicator gets 3:1 against adjacent colors (WCAG 1.4.11). Pair icons with a text label that meets 4.5:1.

The contrast checker. Three layers, most to least convenient:

**The script.** When a runtime is available and the file present, run it instead of computing by hand. Ships in this skill's folder (`contrast-check.py`, next to this `SKILL.md`). `python3` on macOS/Linux, `python` on Windows:
```bash
python3 "${CLAUDE_SKILL_DIR}/contrast-check.py" "#FFFFFF" "#777777"
# normal text: FAIL (4.48 < 4.5)
# large text:  PASS (4.48 >= 3.0)
```
If `${CLAUDE_SKILL_DIR}` isn't available, point the path at this skill's folder directly. The script exists so agents stop hallucinating AA. Takes two hex colors, prints the ratio and the verdict for both text sizes. File missing -> the formula and table below are complete on their own. Never block on the script.

**The formula (WCAG 2.x).**
1. Contrast ratio = (L1 + 0.05) / (L2 + 0.05), where L1 is the lighter relative luminance and L2 the darker.
2. Relative luminance L of one color: convert each channel to 0-1 (`c = hex / 255`), then linearize: if `c <= 0.03928`, `c_lin = c / 12.92`; otherwise `c_lin = ((c + 0.055) / 1.055)^2.4`.
3. `L = 0.2126*R + 0.7152*G + 0.0722*B`.
4. Round the ratio to two decimals and compare: 4.5:1 for normal text, 3:1 for large text (18px+, per R-25). Max ratio is 21.0 (black on white).

**The reference table** (common pairings, computed with the formula):

| Pairing (text on background) | Ratio | Normal text (4.5) | Large text (3.0) |
|------------------------------|-------|-------------------|------------------|
| Black on white | 21.00 | Pass | Pass |
| White on black | 21.00 | Pass | Pass |
| White on #333333 | 12.63 | Pass | Pass |
| White on #666666 | 5.74 | Pass | Pass |
| #777777 on white | 4.48 | Fail | Pass |
| White on #888888 | 3.54 | Fail | Pass |
| White on #999999 | 2.85 | Fail | Fail |
| #555555 on black | 2.82 | Fail | Fail |

Read the table as a sanity check, not a substitute. Any pairing not listed, or anything near a threshold, goes through the formula or the script.

## Keyboard

Removed focus outline. Tell: `outline: none` or `outline: 0` with no replacement focus style. Why: keyboard users can't see where they are; the fastest way to make a UI unusable without a mouse, and R-32 forbids it outright. Fix: keep or replace the outline with a visible `:focus-visible` style meeting the same contrast bar (3:1 against its neighbors). Never set `outline: none` without a replacement.

Mouse-only patterns. Tell: menus that open on hover only, dropdowns that click-open but don't keyboard-open, drag-and-drop with no keyboard fallback. Why: each excludes keyboard and assistive-technology users (R-32). If a control can't be reached and operated by Tab, Enter, or Space, it doesn't exist for a whole group of people. Fix: every interactive element reachable and operable by keyboard (R-32): logical tab order following visual order, activation with Enter or Space, dialogs closable with Escape (R-26).

Broken tab order. Tell: focus jumps around the page, skips content, or lands on hidden elements because DOM order doesn't match visual order. Why: tab order reading code order instead of visual order makes navigation unpredictable (R-32); users lose their place and the page feels broken. Fix: keep source order matching visual order, add skip links for long pages, and never give real content `tabindex="-1"` unless it's part of a controlled focus trap like a dialog.

## Focus & states

Weak or invisible focus indicator. Tell: a focus ring the same color as the background, a ring that only appears on hover, or an indicator thinner than a 1px border. Why: the focus indicator is how keyboard users know where they are. Failing the contrast bar or only showing on hover breaks keyboard-only use (R-32, R-34). Fix: a visible focus indicator on every interactive element, 3:1 against adjacent colors, in every theme you ship. Check dark and light mode.

Color-only feedback. Tell: success, error, and status communicated only by color: red error text, green success border, a tinted chip, with no icon, label, or text. Why: excludes color-blind and low-vision users, and disappears entirely in forced-colors mode. A status depending on seeing hue isn't a status (C-4). Fix: pair every color signal with text, an icon, or a pattern. Error states are text first: "Password must be at least 8 characters", not just a red border.

Missing UI states. Tell: a data view with no empty, loading, or error state, or states that exist but are invisible: a spinner with no text, an empty screen with no explanation. Why: R-27 requires the three states; the accessibility angle is that each must be perceivable and informative, not decorative. A spinner with no context reads as a frozen page to screen-reader users. Fix: every data view has all three states (R-27), each announced or visible: an explicit empty message, a loading state with text, and an error state saying what happened and how to proceed.

## Zoom & mobile use
The layout mechanics behind mobile (breakpoints, scale, grids, overflow, tap targets) are `antislop-layoutmobile`'s concern. This section keeps only the mobile details that exclude people: zooming, and the on-screen keyboard.

Text that cannot zoom. Tell: fixed pixel font sizes, or containers with `overflow: hidden` clipping text at 200% zoom. Why: users must be able to resize text (WCAG 1.4.4). If zooming to 200% clips content or forces horizontal scroll, the text isn't resizable in practice. Fix: fluid type that reflows with zoom, no clipping containers on text, verify the layout holds at 200% zoom on a narrow viewport (R-35).

Mobile keyboard covers the form. Tell: inputs at the bottom of the viewport hidden behind the on-screen keyboard, no scroll-into-view, no room for the input. Why: a form the user can't see or reach is a form they can't complete. A mobile-only exclusion (R-03). Fix: when an input is focused, it scrolls into view above the keyboard, with enough bottom padding that the focused field is never covered. Test with a real device or an emulated keyboard.

## Human skill checklist
Run alongside the core Delivery Gate when the task involves UI. All must be YES:
[ ] every text and background pairing verified against the contrast checker (formula, table, or script), including text over images and gradients? (R-25)
[ ] every interactive component boundary and status indicator meets 3:1 against its background? (non-text contrast)
[ ] focus indicator visible, high-contrast, present on every interactive element in every theme? (R-32, R-34)
[ ] every interactive element reachable and operable by keyboard, dialogs closable via Escape, no `outline: none` without a replacement? (R-32, R-26)
[ ] empty, loading, and error states of every data view present and perceivable, not color-only? (R-27, C-4)
[ ] text resizable to 200% without being clipped, and the mobile keyboard never covers a focused input? (R-35)