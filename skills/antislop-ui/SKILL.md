---
name: antislop-ui
description: "UI and visual skill for antislop. Use when building or editing any interface: color, layout, components, motion. Load with the core."
allowed-tools: Read Write Edit Glob Grep
---
# antislop-ui
Part of the antislop system. Read with `antislop.md` (core). Deep-dives the UI/visual concern: color, layout, components, decoration, structural flow, motion. References core rules by number, never duplicates or renumbers them. Load when the task builds or edits a website, web app, or any interface.

## How to use
- Load with `antislop.md` whenever the task is UI or visual work. Core holds the mechanism (purpose test, three tiers, Delivery Gate); this skill holds UI-specific depth.
- Entry shape: **Tell** (pattern), **Why** (why it reads as slop), **Fix** (what to do), governing core rule cited R-XX.
- The core Delivery Gate remains the gate. The UI Skill Checklist at the end is the UI-specific supplement.

## Visual & color

Generic blue-purple gradient. Tell: blue-to-purple, blue-to-cyan, or purple-to-pink gradients as the primary color treatment, or a full-page colored glow. Why: the most over-represented color treatment in training data. Signals "no brand identity", not "our palette", and marks the design AI-generated at a glance. Fix: pull the palette from `DESIGN.md` or the product's own identity. Keep a gradient only as a hierarchy function with the reason written (R-01). A gradient separating one level from another is craft; the same gradient on every section is a default. Same default family: harsh or rainbow gradients, purple-and-black schemes, neon or pastel palettes, blurred radial orbs behind the hero. Same tell wearing different clothes: color from the model's default, not the brand. All FORBIDDEN as defaults without purpose (R-01).

Excessive glassmorphism. Tell: blur/backdrop-filter on navbar, cards, modals, and sidebar at the same time. Why: blur removes texture and sits every surface in the same frosted layer, flattening hierarchy. When every surface is glass, nothing is foreground. Fix: glass as an accent, not a character trait. Dose cap: at most 1-2 elements (R-10). The surface needing attention gets the glass; everything else stays solid.

Excessive border radius. Tell: every element pill-shaped: buttons, inputs, cards, badges, modals. Why: uniform pill shapes erase the visual language of "this is an input, this is a card". Radius becomes decoration instead of a hierarchy tool. Fix: set a small set of radii in the design system and apply them deliberately (R-11). One generous radius on the primary CTA reads as intentional; the same radius on every element reads as default.

Overly soft shadows. Tell: every component carries a large shadow, so the whole page feels floating. Why: when everything is elevated, elevation communicates nothing. The page loses its ground plane and becomes generic softness. Fix: shadow as an elevation marker only, elevation reason written down (R-12). Most elements sit flat; the one or two that need to lift above the page carry the shadow.

Glow everywhere. Tell: glow on cards, buttons, icons, badges, backgrounds, and borders simultaneously. Why: glow is an attention amplifier; applied everywhere it amplifies nothing, and it is one of the fastest ways to look "made by AI". Fix: reserve glow for a maximum of 1-2 important elements as a focus accent (R-13). Everything else stays matte.

Background grid. Tell: grid squares, blueprint lines, graph paper, dot grids, or thin repeating lines behind content. Why: a default way to make a flat page feel "technical" without real work; texture without intent. Fix: texture/pattern only when it genuinely supports the product's identity, reason written (R-07). A real identity motif (core Part 3) beats a stock grid.

Dark mode default for no reason. Tell: whole page dark simply because it looks "tech", no branding consideration. Why: dark is a decision, not a default. Forcing it reads as following a trend, not serving the product. Fix: choose theme from brand identity, product type, audience (R-21). Developer and creative tools have legitimate reasons for dark; a content-first product usually does not. No strong reason for a fixed theme -> build a working light/dark toggle.

Too many colors in the palette. Tell: 5-7 different colors on one page with no clear design system. Why: a scattered palette has no hierarchy; when every element can be any color, nothing is distinguished. Fix: cap the active palette at 2-3 core colors + 1 accent (R-29), let one core be the neutral base. Restraint is what makes the accent land.

Excessive accent color. Tell: one accent color on buttons, icons, badges, links, lines, backgrounds, and glows at once. Why: an accent stops being an accent the moment it is everywhere; it becomes just another color and the design loses its focal point. Fix: the accent belongs at the key moment only (one deliberate accent, core Part 3). Zero accents is sterile; an accent everywhere is slop. Choose the one or two places it matters.

Sterile default. Tell: flat white or near-white, thin grey borders, small radius, no texture, generic font, no identity. Why: the "safe" result of over-filtering without direction. Not slop, but not design either: a void where a design should be. Fix: a direction problem, not a filter problem. Add `DESIGN.md` or resolve the Design Read (core Part 3), then raise the liveliness dials. The fix is never more bans; it's state the purpose and add energy.

## Layout & components

Monotonous template layout. Tell: hero, subtitle, 2 CTAs, screenshot, feature grid, testimonials, FAQ, CTA, footer, in that order every time. Why: the order is the training-data default, not the product's narrative. Sections appear because the template has them, not because the content needs them. Fix: build structure around actual content needs (R-05, C-3). No testimonials -> no testimonials section. Section order follows the product's story. Match the RHYTHM dial: if 3, sections visibly vary.

Copy-paste feature cards. Tell: identical size, height, icon, layout, padding across all feature cards. Why: uniform cards flatten the content; the features with real weight and the ones without look the same. Fix: create variation reflecting content hierarchy, reason written (R-14). Not every feature needs a card. Flagship may deserve full-width; supporting ones a list.

Bento grid. Tell: a section made of a mosaic of differently-sized cards, some spanning two columns or two rows, filling the space like a tiled dashboard. Why: the default "app-like" landing layout of the last few years, signals nothing about the product. When every section could be a bento, the layout is a template, not a decision. Fix: bento only when the content genuinely has elements of different sizes to show (R-05). If every cell is roughly the same, a simple grid or list is more honest. The RHYTHM dial decides whether sections vary.

Uniform spacing. Tell: padding, margin, and gaps identical across every section. Why: rhythm is a tool; a single spacing value removes it. Sections stop relating, page reads as one flat strip. Fix: whitespace as structure (core Part 3), varied with the RHYTHM dial. Establish a spacing scale, use different levels to separate and connect. Uniform rhythm is a deliberate choice only when the dial says so (R-05).

"How It Works" always 3 steps. Tell: round icon + number 1, 2, 3 + short text, always three steps, always the same shape. Why: the product's real process is rarely a tidy three-step list; the template forces the process into its shape. Fix: present the process as it actually is (R-05). Three steps with round icons is fine if that's genuinely the process; otherwise use whatever shape the real workflow takes, including two steps or five.

"Trusted By" logo bar. Tell: a row of generic company logos directly below the hero. Why: trust claim with no evidence: generic logos, no real customers named, no proof of use. Fix: only real, verifiable logos (R-18, R-36, C-5). No such customers yet -> don't fabricate a logo bar. Real social proof beats a generic one.

"Most Popular" pricing card. Tell: the middle pricing tier always highlighted with a capsule badge. Why: it's the default pattern, which means it's not a decision. When every pricing section does it, the highlighted tier stops meaning anything. Fix: highlight the tier that actually serves the product's goals, write why (R-31). No tier deserves emphasis -> highlight none. Three columns is part of the tell: pricing shown as three tiers whatever the real structure, middle one highlighted. That shape is the default, so it's not a decision (R-05). Use as many tiers as the product really has, highlight the one that serves it.

Demo without a product. Tell: page sells a product never shown working: no real demo, no ToS, no Privacy Policy, just promises. Why: a demo wearing a product's clothes. Every claim is trust with nothing behind it, and missing legal pages are the quiet tell that nothing real exists yet. Fix: show the real product working, or say honestly it's not shipped yet (R-38, C-5). If the page asks for signups or payment, ToS and Privacy Policy must exist. An honest "coming soon" beats a convincing demo.

4-column template footer. Tell: Product / Company / Resources / Legal columns with no variation. Why: columns exist because templates have them, not because the site has that many link groups. Fix: structure the footer around what the product actually links to (R-05). A single column of links can be more useful than four half-empty ones.

Uniform section rhythm. Tell: every section is centered title + subtitle + identical card grid, no variation. Why: identical composition makes sections blur together; the page feels repetitive and flat. Fix: vary composition with the RHYTHM dial (R-05). Alternate text-heavy and visual sections, asymmetric and symmetric layouts. A page where every section follows the same template is designed by a template.

## Decorative elements

Generic AI icons. Tell: sparkle, star, magic, lightning, diamond, cube, robot, or AI orb as feature icons. Why: the generic vocabulary of "AI product"; communicates nothing about the specific feature. Fix: icons genuinely relevant to the content, relevance written when the glyph is generic (R-04). No appropriate icon -> none. The feature label does the work.

Lucide icons. Tell: every icon from the same thin-stroke, rounded-corner library (Lucide or visual clone), all icons sharing one recognizable look. Why: a single default icon library makes every AI site's icons identical; icons stop telling you anything about the product. The glyphs may be relevant; the uniform library look is the tell. Fix: the icon set is a visual choice, not a default (R-04). Pick icons for relevance first; then decide whether the library's weight and stroke suit the product's character. Two "same-ish" icons can still read as yours if the set is a decision, not an import.

Emoji as decoration. Tell: literal emoji scattered through copy, headings, badges, buttons: 🚀 in a headline, ✅ beside every feature bullet, 🔥 on a CTA, 📈 above a chart title. Why: the loudest shorthand for "this was generated, not written". Competes with content for attention and flattens the product's voice into the same cheerful default as every other AI site. Fix: remove emoji from UI text. A concept needing a mark gets a real, relevant icon with the reason written (R-04), or no mark. The copy carries the meaning; the emoji adds nothing.

Small arrows on every button. Tell: `→` or `↗` on almost every button as pure decoration. Why: the arrow becomes a pattern, not a signal. When every CTA has one, none point anywhere specific. Fix: arrows aren't the default identity for buttons (R-08). Keep for the action genuinely benefiting from a direction cue, sized proportionally, purpose written.

Colored left stripe. Tell: a thin colored vertical bar on the left edge of cards, list rows, or section headers, as decoration. Why: the stripe adds color without meaning. The cheapest way to make a card "look designed", so it appears everywhere and says nothing. Fix: the stripe is decoration; it must carry information or go (R-01, R-31). A left edge marking real state (active, warning, new) is a signal. A stripe existing to look designed is a default.

AI capsule badges. Tell: pill shape, thin border, glow, small dot, uppercase, containing "AI Powered", "Beta", "New". Why: the capsule-plus-glow-plus-dot combination is a self-referential badge saying "made by AI, about being made by AI". Adds noise, not information. Fix: badges only when functionally needed, need written, never the full combination (R-09). A real status label is fine; a decorative "AI Powered" pill is not.

Eyebrow badge above the headline. Tell: a small pill sitting directly above the H1, often with a dot and a thin border, holding a category label ("Aplikasi Tagihan UKM", "The platform for teams") the headline beneath already says. Why: the badge duplicates the headline, adding a line of reading without a fact. It lands in the same spot on every generated page, so it reads as template, not decision. With a dot, it borrows status-indicator language for a label marking no state. Fix: cut it and let the headline do the work. If the label carries information the headline doesn't, fold it into the headline or subheadline where it reads as content instead of ornament. A badge above the fold needs a written reason like any other badge (R-09), and a dot inside needs a real state to mark (R-31).

Decorative status dot. Tell: a small colored dot beside a heading, eyebrow, nav item, or label, usually glowing and pulsing on a loop, marking nothing. Borrows the visual language of a live or recording indicator for a page where nothing is live. Why: an attention grab with nothing behind it: a glow plus an endless pulse is a double bid for the eye over a fact that doesn't exist. Reads as AI because generated pages reach for system-status vocabulary as decoration, and the same dot lands in the same place on every one of them. Fix: a dot must mark a real state (active, live, recording, warning). If it does, keep one dot, drop the glow, drop the endless pulse (R-19). If it marks nothing, remove it: a heading needs no indicator to be a heading (R-31).

Generic AI typography. Tell: large monospace headings, or uppercase labels with extreme letter-spacing ("HOW IT WORKS", "FEATURES"). Why: monospace-as-aesthetic and wide-tracked uppercase are shorthand for "technical and modern" without real typographic work. Fix: choose typeface from brand character, not the model's default pick, reason written (R-06). Typography must improve readability and reflect the product. A type choice with a reason beats a trend. The default roster: Inter, Geist, Space Grotesk for sans; Geist Mono, JetBrains Mono, Fira Code for mono. None banned; each valid with a brand reason. The tell is the font showing up because it was the default, not because it fits (R-06).

Fake terminal window. Tell: a styled terminal window with traffic-light dots, a prompt line, and typed-out commands, used as hero or feature visual. Why: the generic "this is a developer tool" costume. The window is decoration; the real product rarely looks like that. Reads as a placeholder for a real screenshot. Fix: if the product is genuinely a terminal or CLI, a real working screenshot is evidence. Otherwise show the actual product UI, not a costume (R-06, C-5). Monospace as aesthetic is already covered by R-06; a fake terminal is that pattern as a component.

Illustrations with no connection. Tell: Undraw, Storyset, or generic 3D blob characters with no real connection to the product. Why: decorative illustrations say the design is decorated, not designed. They fill space without serving content. Fix: illustrations must have a direct connection to the product, connection written (R-22). None exists -> real screenshots or no illustration.

## Structural & flow

Dead navigation. Tell: navbar links to pages or sections that don't exist. Why: dead links are a broken promise; they break trust the moment a user clicks. Fix: every nav item has a real destination (R-24). Unbuilt feature -> leave it out, or label "Coming soon" clearly. The navbar reflects content that actually exists.

Non-functional controls. Tell: buttons do nothing, dropdowns won't open, forms can't submit. Why: the visual is finished, the behavior isn't. The difference between a mockup and a product. Fix: every interactive element has real behavior, or is removed (R-26). Genuinely no destination -> ship a clear `// TODO` plus a visible "Coming soon" label, or don't ship it.

Sections that fill a template. Tell: a section exists because "every AI landing page has one", not because content needs it. Why: template sections are content without purpose; they add length and remove focus. Fix: every section earns its place from the product's content (C-3). Remove sections that only fill a template. Fewer, purposeful sections is stronger than all the defaults.

## App & dashboard
The patterns above are landing-page shapes. These are the app-side equivalents: defaults an agent reaches for when the screen is a dashboard, admin panel, or any signed-in view. The rules broken are the same; only the shape is new.

Default dashboard shell. Tell: left sidebar, top bar, four stat cards, a chart, a table, chosen before anyone asked what the screen is for, identical whether it manages invoices, patients, or servers. Why: the landing-page template problem in an app: a layout picked from memory instead of from the work the screen supports. Swap the labels and it belongs to any product. Fix: name the screen's job and the one decision the user makes on it, build hierarchy around that (C-3, R-20). If the job is "spot the failing job and retry it", the failing jobs are the page and the stat row is a footnote. Sections surviving only because dashboards usually have them get cut (C-3).

Stat cards with invented numbers. Tell: a row of four cards reading 12,483 / 94.2% / $48.2K / 1,204, each with a green "+12% this week" delta. Why: numbers as decoration, and the deltas are worse: a trend claim with no series behind it. Real dashboards have metrics that matter and metrics that don't, so four equal cards is already a hierarchy failure. Fix: show real numbers or none (R-17, R-38). Wire the cards to real data, or ship the one metric that is real. A delta appears only when the comparison period is real and named. Prototype -> label the values as placeholder where the user can see it (R-38).

Filler activity feed. Tell: "Sarah Chen updated a document, 2 hours ago", repeated with rotating names and avatars. Why: invented people, invented events. The testimonial section wearing a different layout; makes an empty product look busy. Fix: the feed shows real events or doesn't ship (R-18, R-38). An honest empty state beats a fabricated feed, and tells the user what to do first (R-27).

Charts without a question. Tell: a line or donut chart placed because the space looked bare, with a generic title ("Overview", "Performance") and no axis the reader can act on. Why: a chart is an answer. Without the question it's texture, costing more attention than a sentence would. Fix: write the question the chart answers before drawing it, put it in the title ("Failed jobs per hour, last 24h"). A sentence answers it better -> write the sentence (C-3). Chart segments still need 3:1 contrast against neighbours (R-25).

Generic table columns. Tell: Name, Status, Date, Actions, whatever the rows actually are, with a three-dot menu on every row. Why: columns come from the table component, not the data. The user scans for the field deciding their next move and it isn't there. Fix: pick columns from the decision the user makes in this table, put the deciding field early. The row menu holds actions that exist; anything that does nothing comes out (R-26).

Filler data in fields and columns. Tell: empty form fields and table columns filled with fake but plausible data: `John Doe`, `johndoe@example.com`, `"Let's build something"`, phone numbers and dates belonging to nobody. Why: fabricated content disguised as real. Reads fine in a mockup, falls apart the moment a real user looks: the name isn't a customer, the email isn't a lead, the message is a tagline. The strongest tell the screen was generated, not built. Fix: leave empty cells empty, or use placeholders that clearly say what goes there: `Your Name`, `email@example.com`, `Drop your message here...`, or `[REAL DATA]` when a value is expected (R-23, R-38). Real data goes in when it exists. Generic filler copy like "Let's build something" is buzzword slop and doesn't belong in a data column (R-16).

Placeholder empty and loading states. Tell: "No data available" with an illustration, a bare spinner, or a full-page skeleton mimicking a layout the real data never fills. Why: R-27 requires the states, and these technically have them, but they tell the user nothing: no cause, no next action, no idea whether this is normal. Fix: an empty state says why it's empty and gives the one action that fills it ("No jobs yet. Run a sync to see results here"). A loading state says what it's loading. An error state says what failed and what to do next (R-27). First run, filtered to nothing, and permission denied are different screens and read differently.

## Motion

Endless pulses and loops. Tell: elements that pulse, bounce, or float forever with no user trigger. Why: perpetual motion is noise; competes with content for attention and never lets the user rest. Fix: motion must have a clear UX purpose, written down (R-19). Animation guides attention to a moment; it doesn't run on a loop. If the MOTION dial is 1 (hover states only), an endless loop is a FAIL against the declared dial.

Template animations stacked. Tell: every element uses Fade Up + Fade In + Floating + Scale + Bounce simultaneously. Why: a page where everything animates has no focal point; motion becomes wallpaper. Fix: choreograph motion to a purpose and to the MOTION dial (R-19). Not everything moves. The hero speaks, supporting elements stay calm. Claimed "cinematic" pages must actually move; claimed "static" pages must not.

## UI skill checklist
Run alongside the core Delivery Gate for UI work. All must be YES:
[ ] palette derived from `DESIGN.md` or a written brand identity, not the default gradient set? (R-01, R-29)
[ ] accent used at the key moment only, not spread across every element? (core Part 3, one deliberate accent)
[ ] copy free of decorative emoji scattered through headings, bullets, buttons? (R-04)
[ ] section compositions vary according to the declared RHYTHM dial instead of repeating one template? (R-05)
[ ] layout free of the default AI shapes: bento-grid mosaic, fake terminal window, three pricing columns, left-edge color stripes with no meaning? (R-05, R-01)
[ ] space above the H1 clear of a pill badge holding a label the headline already says? (R-09)
[ ] every nav item and interactive element has a real destination or behavior, or a visible "Coming soon" label? (R-24, R-26)
[ ] motion follows the declared MOTION dial and serves a written purpose, with no endless loops? (R-19)
[ ] glass, glow, shadow, radius used at their dose caps, not as a page-wide default? (R-10, R-11, R-12, R-13)
[ ] every colored dot and status light marking a real state, with no decorative glow or endless pulse? (R-13, R-19, R-31)
[ ] on an app screen, layout built around the decision the user makes there, rather than the sidebar plus stat row plus chart plus table default? (C-3, R-20)
[ ] every number, delta, feed entry, and table row real or a labelled placeholder, with no invented metrics? (R-17, R-18, R-38)
[ ] empty form fields and table cells stay empty or carry honest placeholders (Your Name, email@example.com) instead of fake-looking data (John Doe, johndoe@example.com)? (R-23, R-38)
[ ] empty, loading, and error states name the cause and the next action instead of saying "No data"? (R-27)
[ ] page holds up at every breakpoint, theme, and state, and passes keyboard-only use? (R-03, R-34, C-4)