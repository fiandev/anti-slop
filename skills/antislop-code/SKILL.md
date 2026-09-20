---
name: antislop-code
description: "Code comment hygiene for AI coding agents: remove generic AI-slop comments, keep the valuable ones, never touch the code."
allowed-tools: Read Write Edit Glob Grep
---
# antislop-code
Part of the antislop system. Read together with `antislop.md` (core). Filters comments that read as generically AI (decorative, restating the obvious, stiff, loud) while preserving comments carrying real information. References core rules by number, never duplicates or renumbers them. Load when the task writes or edits code comments.

## How to use
- Load with `antislop.md` whenever the task touches code comments. Core holds the mechanism (purpose test, three tiers, Delivery Gate); this file holds comment-specific depth.
- Entry shape: **Tell** (pattern), **Why** (why it reads as slop), **Fix** (what to do), governing core rule cited as R-XX.
- **Scope guardrail:** this skill only modifies comments. NEVER modify executable code, identifiers, imports, formatting, indentation, whitespace, control flow, or logic. When in doubt, leave the code untouched.
- The core Delivery Gate remains the gate. The Code Comment Checklist at the end of this file is the comment-specific supplement to run alongside it.

## Comments that add nothing

Decorative separators. Tell: banner comments from repeated characters, ALL CAPS labels, or box drawing around a section name (`// =======================` around Authentication, `// -------- WORKFLOW --------`, `/* ---- ROUTES ---- */`). Why: the decoration is the message; a label wrapped in `=` or `-` signals "AI made this" with no information added, and ALL CAPS reads as shouting. Fix: a single plain line, or remove entirely if the label adds nothing (R-31).

Restating the obvious. Tell: a comment repeating what the next line or declaration already shows (`// Initialize the variable` above `let count = 0`; `// User class` above `class User {}`; `// Validate user` above `function validateUser()`; `const userAge = 25; // User age is 25`). Why: doubles reading load, adds nothing; the code already says it. Fix: remove, leave the line of code alone.

Workflow narration. Tell: comments narrating flow step by step (`// Step 1: Validate input`, `// Step 2: Process request`, `// Step 3: Return response`; `// First...`, `// Next...`, `// Finally...`). Why: control flow is visible in the code; numbering reads as a checklist, not an explanation. Fix: remove. If the flow is genuinely hard to follow, that's a structure problem, not a missing-comment problem.

Empty labels. Tell: generic labels with no information behind them (`// Main logic`, `// Core logic`, `// Business logic`, `// Helper function`, `// Entry point`, `// Error handling`, `// Note: This is important.`, `// Important: Please read.`). Why: the label names a category, not a fact; "Main logic" tells the reader nothing they couldn't infer. Fix: remove unless the label carries specific information. "Note: retries happen only on 5xx" earns its place; "Note: this is important" does not.

Vague placeholders. Tell: comments promising future work without saying what (`// TODO: Improve this`, `// Future improvements`, `// Additional optimization can be added here`, `// Add more validation`). Why: a vague TODO is noise; it names a feeling (this could be better) instead of a task (what, and why). Fix: remove. Keep a TODO only when it names a specific task with enough context to act on.

Signature echo. Tell: documentation only restating the signature, e.g. a JSDoc block repeating `@param price The price.` / `@returns Total price.` for a function whose name and parameters already say it all. Why: docs that echo the signature add length, not understanding. Fix: simplify or remove the echo. KEEP documentation explaining business rules, edge cases, assumptions, algorithms, limitations, side effects, API behavior, or security implications. Never strip real documentation.

Decorative emoji. Tell: emoji as comment decoration (`// ✅ Validation`, `// 🚀 Performance`). Why: visual noise in code, and the set (✅, 🚀, 🔒) is AI default vocabulary. Fix: plain English, or remove if the label adds nothing.

End markers. Tell: comments only marking the end of a block (`} // end if`, `# End of function`, `// End processOrder`). Why: the closing brace already ends the block; the marker exists out of habit. Fix: remove. Rare case where it genuinely helps in a long file: keep only where it prevents confusion, not as a habit.

## How it should read

The over-explained comment. Tell: one comment running several lines, stacking reasons, context, and history around a fact that fits in one line: a four-line block explaining that a stub sits on PATH, which release introduced the workaround, and what broke before it. Every sentence is true; the length is the tell. Why: a person leaves a note, a generator writes a case. Padding a one-line fact into a paragraph, building a "because X, so Y, therefore Z" chain, or citing the issue number and the fixing version are the same flourish as any other AI pattern, burying the one line that matters. Fix: cut to the constraint alone: one line, two at most, never three. Keep the platform trap, silent failure, protocol rule, performance cost. Drop the issue number, version history, reasoning chain.

Line-by-line narration. Tell: a comment on every trivial statement, narrating each line as written (`// Initialize count`, `// Loop items`, `// Get item`, `// Increment`, `// Return result`). Why: when every line is commented, none of the comments matter; the reader must check each to find the one carrying meaning. Fix: one concise comment per logical block, not per line. No comment needed -> write none.

Stiff or loud wording. Tell: comments that sound formal, long, or shout ("This function is responsible for validating whether the supplied credentials are valid before continuing with the authentication process"; `// MAIN LOGIC` in caps). Why: formal and loud wording reads as generated, not as an engineer leaving a note for the next person. Fix: short, sentence-case lines in a natural developer voice (`// Validate credentials before issuing a token.`). Good comments explain why, not what, and stay short.

## Not a ban (preserve these)
Never remove comments explaining: business logic and intent; architectural decisions; security considerations; performance trade-offs; concurrency behavior; protocol details; API contracts; workarounds; edge cases and assumptions; licensing and legal notices.
Must stay:
```js
// Stripe may retry webhook deliveries for up to three days.
// Ignore duplicate events using the event ID.
```
A comment earns its place when it explains something the code doesn't already show: the reason, the constraint, the non-obvious behavior.
Earning a place says what may stay, never how long it may run. A workaround note is one line about the workaround, not a paragraph about it. The example above is two lines because two facts are real, not because two lines is a target. This list is the most common reason a comment survives a review it shouldn't: the content is legitimately valuable, so the length goes unexamined. Value is not length.

## Code comment checklist
Run alongside the core Delivery Gate when the task touches comments. All must be YES:
[ ] every comment adds information the code doesn't already show? (R-31)
[ ] avoids decorative separators, ALL CAPS banners, box-drawn headers?
[ ] avoids restating the obvious line, declaration, or signature?
[ ] avoids step-by-step workflow narration?
[ ] avoids empty labels and vague TODOs that name no task?
[ ] avoids decorative emoji and end markers?
[ ] density is one comment per logical block, not per line?
[ ] every comment one line, or two only when the second carries a new fact?
[ ] remaining comments read short, natural, sentence case?
[ ] scope guardrail held: only comments changed, code untouched?