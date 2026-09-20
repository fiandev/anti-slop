---
name: antislop-copywriting
description: "Copy and text skill for antislop. Use when writing or editing prose: headlines, tone, CTAs, and anti-AI-writing patterns. Load with the core."
allowed-tools: Read Write Edit Glob Grep
---
# antislop-copywriting
Part of the antislop system. Read with `antislop.md` (core). Deep-dives copy: headlines, CTAs, tone, value props, and the patterns making AI prose easy to spot. References core rules by number, never duplicates or renumbers them. Load for marketing copy, product copy, landing-page text, or any prose people read.

## How to use
- Load with `antislop.md` whenever the task is copy. Core holds the mechanism (purpose test, three tiers, Delivery Gate) and the hard bans (R-02, R-15, R-16, R-17, R-18, R-36, R-38). This skill holds copy-specific depth.
- Entry shape: **The pattern**, **Why it reads as AI**, **Before** (slop), **After** (fix), governing core rule cited R-XX.
- Two rules over everything below:
  - **Never invent facts** (R-17, R-36, R-38). A rewrite adds no fact, name, number, date, quote, or citation not in the source or supplied by the user. Specificity comes from the source or user, not the rewrite. Need real detail? Ask, or write the plain version without it.
  - **Do not over-sterilize.** Avoiding AI patterns is half the job. Copy with no voice is as obviously machine-made as copy full of AI tells (R-37). When the user supplies a voice, keep it.
- The core Delivery Gate remains the gate. The Copywriting Skill Checklist at the end is the copy-specific supplement.

## Tone & voice

Empty AI vocabulary. Pattern: verbs and abstract nouns stacked to sound impressive with no content: unlock, elevate, empower, delve, showcase, testament, landscape (abstract), journey, robust, game-changer, next-level, seamless, cutting-edge, revolutionary. Why: these appear far more in machine-written text; they signal intent to impress, not inform, and are the fastest way to mark a page as AI. Before: "Unlock the power of seamless collaboration to elevate your team's journey to the next level." After: "Work with your team in one shared space." Rule: R-16, R-36.

Significance inflation. Pattern: "the future of X", "marking a pivotal moment", "a testament to", "revolutionizing", "a new era of". Why: no evidence behind the claim, and it reads the same regardless of what the product does. Ceremony where content should be. Before: "Our platform is marking a pivotal moment in the evolution of team productivity, ushering in a new era of work." After: "Our platform cuts the time your team spends on status meetings." Rule: R-36, C-5.

Empty claims and social proof with no evidence. Pattern: "Trusted by thousands of teams", "industry-leading", "world-class", "loved by customers everywhere", nothing named or verifiable. Why: a trust claim without evidence is a confession; it fills the space a real customer name, number, or use case should occupy. Before: "Trusted by thousands of teams worldwide. Industry-leading technology loved by customers everywhere." After: "Used by the support teams at [customer names, only if real]. If there are no real customers to name, cut the claim entirely." Rule: R-17, R-18, R-36, C-5.

Weasel attributions. Pattern: "Experts say", "industry observers", "people report", "leading analysts believe", no one named. Why: the attribution makes an unsourced claim feel authoritative. Real authority -> name it; if not, the claim doesn't get a costume. Before: "Experts say this approach dramatically improves conversion." After: "[Name the source or cut the sentence. With a real source: \"In a 2024 study by [named firm], this approach improved conversion by [real figure].\"]" Rule: R-36, C-5.

Persuasive authority tropes. Pattern: "at its core", "the real question is", "what really matters", "fundamentally", "the deeper issue", "the heart of the matter". Why: they pretend to cut through noise to a deeper truth, then restate an ordinary point with extra ceremony. Before: "At its core, what really matters is whether your team can move faster." After: "Whether your team can move faster depends on how quickly you can merge changes." Rule: R-36.

Chatbot closers. Pattern: "I hope this helps!", "Let me know if you have any questions", "Would you like me to expand on this?", "You're welcome!". Why: conversation artifacts, not copy; they appear when chat output is pasted into a deliverable. Before: "Here is an overview of our pricing. I hope this helps! Let me know if you'd like me to break down any tier." After: "Here is our pricing. The Starter tier includes three seats and community support." Rule: R-36.

Fake-candid openers. Pattern: "Honestly?", "Let's be honest", "Here's the thing", "Real talk", as a theatrical pause before an ordinary point. Why: a person being honest usually just says it; pause-and-reveal is manufactured intimacy. Before: "Is it worth the price? Honestly? It depends on how often you'll use it." After: "Whether it is worth the price depends on how often you'll use it." Rule: R-36.

Signposting announcements. Pattern: "Let's dive in", "Here's what you need to know", "In this article we'll explore", "Without further ado". Why: announcing what you're about to do instead of doing it is meta-commentary; slows the reader, gives a tutorial-script feel. Before: "Let's dive into how caching works in Next.js. Here's what you need to know." After: "Next.js caches data at multiple layers, including request memoization, the data cache, and the router cache." Rule: R-36.

All-caps emphasis. Pattern: a whole sentence, clause, or phrase in ALL CAPS inside a paragraph to shout: "The launch is ready and WE NEED TO MOVE NOW before the window closes." Why: caps-as-emphasis is a blunt instrument used to manufacture urgency instead of writing emphasis into the sentence; in long text it reads as shouting and flattens real peaks. Before: "This is our last chance to win this customer, and WE MUST ACT IMMEDIATELY before they choose a competitor." After: "This is our last chance to win this customer. If we do not respond today, they will choose a competitor." Rule: R-36 (R-06 covers uppercase labels with wide tracking as a design choice; this is the prose case). Not a ban: a genuine headline, a deliberately shouted line in a voice that shouts, or a single all-caps word once as an accent can keep caps. The tell is caps sentence after sentence doing the words' work. Minimize, don't strip every cap.

Actorless passive. Pattern: passive with the actor deleted: "the decision was made to sunset the free tier", "the pricing page has been updated", "mistakes were made". Why: the model doesn't know who acted, so it writes around it; the team that shipped it does know. Deleting the actor also removes accountability, which is why it survives in corporate copy. Before: "The pricing page was updated to reflect the new tiers." After: "We rewrote the pricing page to show the new tiers." Rule: R-02. Not a ban: passive is right when the actor is unknown, irrelevant, or deliberately withheld ("the server was restarted at 03:00"), and when the object is the paragraph's real subject. The tell is passive by default, page after page, with an available actor.

Inanimate subject, human verb. Pattern: an abstraction given agency: "the data tells us", "the design decides", "the complaint becomes a fix", "the roadmap wants to focus on retention". Why: sounds active while naming nobody, passing a passive check and still hiding the actor; also flatters the product, since a dashboard that "understands" does what no dashboard does. Before: "The dashboard understands what your team needs and surfaces the right numbers." After: "The dashboard opens on the three metrics your team checks every morning." Rule: R-02, R-16. Not a ban: ordinary product verbs and established idioms are fine ("the report shows", "the form submits", "the filter narrows the list"). The tell is a verb needing a mind behind it: understands, knows, decides, wants, believes, cares.

## Rhythm & structure

Rule of three overuse. Pattern: every idea forced into a trio to sound complete: "innovation, inspiration, and insights". Why: real lists have the number the content requires; a forced trio is a rhythm tell appearing across every section at once. Before: "Attendees can expect keynote sessions, panel discussions, and networking opportunities. They'll leave with innovation, inspiration, and industry insights." After: "The event includes talks, panels, and time for informal networking between sessions." Rule: R-05, R-36.

Negative parallelism and tailing negations. Pattern: "It's not just X, it's Y", "Not only X, but also Y", plus clipped fragments tacked on as emphasis ("no guessing", "no wasted motion"). Why: a formula reached for to sound emphatic, whether or not the emphasis is earned. Before: "It's not just a dashboard, it's a command center. The options come from the selected item, no guessing." After: "The dashboard shows the data you select. The options come from the selected item without forcing you to guess." Rule: R-36.

Aphorism formulas. Pattern: "X is the language of Y", "X is the currency of Z", "X is not a tool but a mirror", "Efficiency becomes a trap when". Why: a reusable formula that sounds profound without adding precision; it gestures at a point instead of stating it. Before: "Symmetry is the language of trust. Efficiency becomes a trap when teams forget the human layer." After: "Symmetric layouts feel more predictable to users. Teams can over-optimize workflows and miss how people actually work." Rule: R-36.

Staccato drama. Pattern: a run of short declarative fragments to manufacture a punchline: "It had no preference. No prior. No nostalgia." Why: one short sentence for emphasis is fine; a run sounds engineered, the rhythm even, the effect theatrical. Before: "Then the old rules were gone. No templates. No defaults. No safety." After: "The old rules no longer applied, and every page had to be designed from scratch." Rule: R-36.

Synonym cycling. Pattern: swapping synonyms to avoid repeating a word: "the protagonist faces a challenge, the main character must adapt, the central figure persists". Why: models rewrite to dodge repetition penalties; human writers repeat the clearest word when it's clearest. Before: "The checkout is fast. The process is quick. The flow is speedy." After: "The checkout is fast. Everything happens in three clicks." Rule: R-36.

False ranges. Pattern: "from X to Y" where X and Y aren't on a meaningful scale: "from onboarding to scale", "from first click to final invoice, and everything in between". Why: an impressive-sounding frame covering nothing specific. Before: "From first touch to final invoice, and everything in between." After: "Handles quotes, invoices, and payment reminders." Rule: R-36.

## Honesty & evidence

Fabricated specifics. Pattern: invented numbers, testimonials, names, dates, or features that look realistic but aren't real. Why: a specific-looking fabrication is worse than a vague claim, because it reads as honest while being false. The one pattern that's a defect even when it sounds more human. Before: "Trusted by 10,000+ teams. \"Antislop cut our review time in half.\" - Sarah Chen, VP Engineering at [fictional company]." After: "If no real customer exists, write no number and no quote. Say what the product does instead. Any real statistic needs a real source (R-17, R-36)." Rule: R-17, R-18, R-36, R-38, C-5.

Speculative gap-filling. Pattern: when the writer doesn't know a fact, they write a sentence about not knowing it, then invent plausible filler: "the company was likely founded in the 1990s", "she maintains a low profile". Why: a guess dressed as fact; no source found, so the gap gets papered over. Before: "While specific details are limited, the founder likely started small and grew through word of mouth." After: "The founding details are not documented in our sources. (Or omit the sentence entirely. State a date only if a source provides one.)" Rule: R-17, R-36.

Generic positive conclusion. Pattern: "The future looks bright", "Exciting times lie ahead", "This is a major step in the right direction". Why: an upbeat send-off restating nothing and promising nothing; pads the ending with optimism instead of information. Before: "The future looks bright for our customers as we continue our journey toward excellence." After: "(Cut the sentence. End on the last concrete fact, or state real plans if they exist.)" Rule: R-36.

## Hygiene & markdown

Em dashes. Pattern: the em dash character (`—`) as an aside or connector: "institutions — not the people — continue". Why: one of the most reliable AI tells; the core bans it outright. Rule: R-02 forbids the em dash in any text. Replace each one, roughly in order of preference: a period (new sentence), a comma (tight aside), a colon (introduce an explanation), parentheses (true aside), or restructure. Also catch spaced em dashes (` — `) and double hyphens (` -- `) used the same way. Before: "The policy — announced without warning — affects thousands of workers." After: "The policy, announced without warning, affects thousands of workers." Before: "You don't say \"Netherlands, Europe\" as an address — yet this mislabeling continues." After: "You don't say \"Netherlands, Europe\" as an address, yet this mislabeling continues." False positive: many editors and journalists use em dashes deliberately; on its own an em dash is not proof of AI. It counts in a cluster with other tells (R-02 still bans it in output, but don't rewrite the user's deliberate style without saying so). Voice sample: a user sample using em dashes is a direction, not agent copy. Surface it per R-37 (name the character, name the rule, ask), then match the sample's frequency only if the owner keeps it. Never keep or cut them silently.

Boldface overuse. Pattern: every key term bolded mechanically: "**OKRs**, **KPIs**, **BMC**". Why: emphasis everywhere is emphasis nowhere; the page shouts. Before: "It blends **OKRs**, **KPIs**, and **visual strategy tools** for planning." After: "It blends OKRs, KPIs, and visual strategy tools for planning." Rule: R-36. Carve-out: the structural labels inside the antislop rules themselves (the `**FORBIDDEN**` / `**REQUIRED**` markers in `antislop.md`) are documentation conventions, not mechanical bold-every-key-term, and are exempt.

Excessive quotation marks. Pattern: long text studded with quotes: quoting words that don't need it, scare quotes around ordinary terms, quotes as default emphasis or hedging. The page reads quoted rather than written. Why: models reach for quotes as a default way to add distance, irony, or emphasis without writing it into the sentence; dense quoting is a reliable machine tell in longer text. Before: "The \"solution\" \"streamlines\" your \"workflow\" so you can \"focus\" on \"what matters.\"" After: "The solution streamlines your workflow so you can focus on what matters." Rule: R-36. Not a ban: dialogue, short stories, quoted real sources, and titles of works keep their quotes. The tell is quotes doing the sentence's work. One scare quote used once for a real reason is fine; a cluster is not. Minimize, don't strip quotes that carry meaning.

Inline-header lists. Pattern: list items starting with a bolded header plus colon: "- **User Experience:** The UX has been improved". Why: the header restates what the item already says; a formatting habit, not a structure. Before: "- **User Experience:** The interface is easier to use. / - **Performance:** Load times are faster. / - **Security:** Data is encrypted." After: "The update improves the interface, speeds up load times, and encrypts data in transit." Rule: R-36. Carve-out: the `- **Tell:**` / `- **Why:**` / `- **Fix:**` headers structuring every antislop skill entry are a documentation convention, not the header-restates-the-item habit, and are exempt.

Emojis in headings. Pattern: decoration emojis leading headings or bullets: 🚀 Launch, 💡 Key insight, ✅ Next steps. Why: the emoji carries no information; it decorates instead of communicating. Before: "🚀 **Launch Phase:** The product ships in Q3 / 💡 **Key Insight:** Users prefer simple pricing" After: "The product ships in Q3. User research showed a preference for simple pricing." Rule: R-36.

Filler phrases. Pattern: "In order to" for "to", "Due to the fact that" for "because", "At this point in time" for "now", "It is important to note that" for nothing. Why: filler inflates the sentence without adding meaning; padding added to sound formal. Before: "In order to achieve this goal, it is important to note that we need more data." After: "To reach this goal, we need more data." Rule: R-36.

Excessive hedging. Pattern: multiple qualifiers stacked on one claim: "could potentially possibly", "may perhaps". Why: hedging everywhere sounds evasive; one qualifier does the work. Before: "This could potentially possibly be the reason the feature went unused." After: "This may be why the feature went unused." Rule: R-36.

## What NOT to flag
A clean human writer can hit several patterns above with no AI involvement. Before editing, sanity-check that you aren't gutting legitimate prose. These are NOT reliable indicators on their own:
- Perfect grammar and consistent style. Many writers are professionals or have been edited. Polish != AI.
- Mixed casual and formal registers. Often signals a real person, not a chatbot.
- "Bland" or "robotic" prose. AI prose has specific tells; generic dryness without those tells is just dry writing.
- Formal vocabulary. AI overuses *specific* words (see Empty AI vocabulary), not all fancy words. Don't flatten a precise word just because it sounds brainy.
- Common transition words in isolation. One "however" or "additionally" is not a tell; they count only when piled up.
- Curly quotes alone. macOS, Word, and most CMSes auto-curl by default. Count only when stacked with other tells.
- Em dashes alone. Editors and journalists use them. Evidence only inside a cluster.
- One short emphatic sentence. Humans use clipped sentences to land a point. Flag staccato drama only when several fragments appear in a row.
- Unsourced claims. Most of the web is unsourced. Lack of citations proves nothing.
- Secondhand text. Don't rewrite phrases inside quotations, titles, proper names, or examples where the phrase is being discussed rather than used.

Look for clusters, not isolated tells. A single em dash means nothing. Em dashes + rule of three + "vibrant tapestry" + a generic conclusion is a confession. This matches the core's guidance: Part 1 is a diagnostic scan, not a ban list.

## Signs of human writing (preserve these)
Lean toward leaving the prose alone when you see these. They're evidence of a real person, and over-editing destroys what makes copy sound human:
- Specific, unusual, hard-to-fabricate detail. A real address. A weird quote. LLMs round off specifics; humans hoard them.
- Mixed feelings and unresolved tension. "I think this is mostly good, but it bothers me." LLMs default to clean takes.
- Dated, era-bound references. Slang, memes, or in-jokes mapping to a specific year and subculture.
- Variety in sentence length. Real writing alternates short and long. AI tends toward an even, mid-length cadence.
- Genuine asides and self-corrections. "(I keep wanting to say 'almost' here, but it really was certain.)"

## Voice calibration (optional)
If the user provides a sample of their own writing, match it before rewriting:
1. Read the sample first. Note sentence lengths, vocabulary, paragraph openings, punctuation, recurring phrases.
2. Match those habits instead of merely deleting AI patterns. Don't upgrade casual words or regularize deliberate quirks.
3. The sample outranks this skill's style rules, except where R-02 applies. R-02 governs copy the agent authors; a sample using em dashes is a direction, so it goes through R-37's conflict protocol, and you match its frequency only if the owner keeps it. R-02 applies in full to any copy the user did not authorize.
Without a sample, use the defaults above. Matching the author beats scrubbing the tell.

## Draft, audit, final
Run before delivering copy:
1. Draft. Rewrite applying the patterns above. Check it reads naturally aloud, varies sentence length, prefers specific detail and simple constructions, keeps the appropriate register.
2. Audit. Ask two questions and answer briefly: "What makes this obviously AI generated?" and "Does it state any fact, name, number, date, or citation that is not in the source?" A fabrication is a defect even when it sounds more human than the vague original.
3. Final. Revise to address both answers. Check for em and en dashes one last time (R-02). A hit means the draft is not done.

## Copywriting skill checklist
Run alongside the core Delivery Gate for copy work. Every line must be true:
[ ] no fabricated numbers, testimonials, names, dates, or claims; everything real or a labeled placeholder (R-17, R-18, R-36, R-38)
[ ] buzzwords from R-16 and the Empty AI vocabulary list replaced with specific, evidenced language
[ ] no em dashes in the output (R-02); if the user's own sample voice uses them, they were surfaced under R-37 and the owner kept them
[ ] no excessive quotation marks: quotes only where they carry meaning (dialogue, real citations, titles), not as default emphasis (R-36)
[ ] no all-caps emphasis clauses: emphasis written into the sentence, not shouted with caps (R-36)
[ ] every sentence names its actor: no actorless passive, no abstraction given a human verb, where a real subject was available (R-02, R-16)
[ ] CTAs specific to the action, not generic templates (R-15)
[ ] no AI-rhythm tells: no forced rule of three, no negative parallelism, no staccato drama, no aphorism formulas, no false ranges (R-36)
[ ] voice present: the copy has a real voice (the user's sample or a clearly chosen tone), not a sterile default (R-37)
[ ] read aloud: the copy sounds like a person wrote it, not like a model padded it