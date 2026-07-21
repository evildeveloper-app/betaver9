# Prizm design direction — saved notes (do not lose)

Agreed direction from the Ducat-inspired review (July 2026). "Do all" was approved.

## The Ducat lessons to apply (not copy)

1. **Date rail, unboxed.** Vertical date text floating in the left margin — no border, no background, muted gray. Shown ONCE per day-group, not per row. Rows grouped by day. (First attempt used a bordered gold tab per row — rejected, too cluttered.)
2. **Air instead of boxes.** Remove card backgrounds/borders from list rows; use whitespace + short hairline dividers that don't span full width.
3. **Hierarchy through weight.** Bold (possibly uppercase) transaction names, big bold amounts, small muted metadata. Currency sign and minus LIGHTER than the number (e.g. muted "- A$", bold "199,999.00").
4. **Warm paper background.** Light theme base becomes a soft cream instead of near-white — suits the gold accent.
5. **Sentence insight on Home.** One plain-language line with selective bolding, e.g. "You've spent **$X** today, and have **no upcoming payments** this week." Data already computed in app.
6. **Chat-style Scribe bar (optional, later).** Promote Scribe to a persistent bottom input like Ducat's "Describe your transaction". User's call — Scribe currently deliberately buried in Beta.

## More Ducat patterns (from 2nd batch of screenshots — edit sheet, subscription form, reports, subs list, picker)

7. **Big amount = two weights, one line.** Currency symbol in light gray, the number in heavy black: "A$" muted + "800" bold. Applies to the amount editor, stat headers, everywhere a big number appears. Prizm should mute the currency glyph app-wide.
8. **Detail rows = icon + label + value, hairline between.** Edit/New forms are a flat list: small gray leading icon, muted label on the left ("Paid to", "For", "On", "Category"), bold value right-aligned, thin full-bleed divider. No boxed fields. This is cleaner than Prizm's current boxed `.finput` look for read/summary rows.
9. **Dashed divider under the hero amount.** A single dashed rule separates the big amount block from the detail list below. Signature Ducat touch — subtle, worth borrowing on edit sheets and stat headers.
10. **Category bars: soft gradient fills, rounded, value as a pill.** Horizontal bars with a light-tinted gradient (category color → transparent), big rounded ends, amount sitting at the right end. Muted "A$1.8K" abbreviations. Much softer than Prizm's flat 5px bars.
11. **Pastel scalloped category icons.** Each category has a flower/scallop-shaped badge in a pale tint of its color with a small line glyph. Distinctive and consistent — a possible replacement for Prizm's rounded-square emoji tiles.
12. **List rows carry a leading brand/category badge + two-line text.** Merchant name bold uppercase, sub-label muted underneath ("Renews in 6 days"), value + date stacked on the right. Short hairline between rows, never a boxed card.
13. **One sentence summary, selectively bolded — everywhere, not just Home.** Reports: "You have **4 subscriptions** and around **A$1,000.00 due** by month end." Same device on every screen's right rail. Green-muted connective words, black key facts.
14. **Toggles are green pills; primary action a green pill button** ("Confirm", "Save"). Prizm's accent is gold — our version uses gold pills the same way.
15. **Everything on warm paper (#F3EEE2-ish), pure white only for modals/sheets.** Reinforces lesson 4.

Net: the "clean" comes from NO boxes on rows, hairlines instead of borders, big two-weight numbers, muted connective text with bold facts, soft rounded data-viz, and one warm background. That's the target for the Prizm design pass.

## PRIZM DESIGN LANGUAGE (locked) — Ducat's grammar, Prizm's vocabulary

Psychology to adopt (Ducat's "soul"): money is stressful → UI adds zero noise; whitespace = "you're in control." One hero per screen, everything else recedes. Plain sentences not dashboards. Structure pushed to the margins. Hierarchy from type weight/size only — never boxes/borders/rainbow color. A few crafted signature details repeated everywhere. Restraint reads as luxury; warmth as reassurance; one idea per glance.

Prizm's own body for that soul — metaphor is a PRISM: light, facets, a single gold thread through a dark (Signature) or ivory (Light) field. Luxury-quiet, not friendly-quiet. Shares ZERO look with Ducat's green/cream/pastel-rounded style.

Expression rules:
- Air instead of boxes — kill row card borders, hairline rules, let it breathe. (Biggest shared move.)
- Margin spine — vertical date = thin, unboxed, gold-muted spine down the ledger; grouped once per day. NOT a bordered tab (v1 attempt rejected).
- Two-weight numbers — currency glyph dimmed, number heavy, in Prizm's editorial display face (Fraunces/Sora), not a rounded sans.
- Plain sentence header on every screen — key facts threaded in GOLD, serif voice (not Ducat green).
- Signature motif — faceted gem/spark chips for categories (vs Ducat's scalloped flowers); spark as punctuation.
- Warmth from gold + ivory "paper" Light theme; keep jewel-dark option. Data-viz = soft rounded fills tinted from gold/category hues, never a pastel rainbow.

ALLOWED to borrow directly from Ducat (craft, not identity): the animation feel (smooth spring easing, gentle entrance/stagger) and the overall breathiness/spacing. User OK'd taking these.

## Still pending from the original 2-step plan
- Step 2: one distinctive typeface app-wide (shortlist: Space Grotesk / Fraunces / Sora). Show user before shipping.

## Standing constraints (user's rules)
- Work in `Beta Mode - New Developments`, never touch `Prizm Finance` (stable) or the marketing site.
- Bump service-worker CACHE_VERSION on every ship (beta currently `prizm-v5.0-beta.1`).
- Verify with `node --check app.js` + tag balance after changes.
- Don't undo: Apple-style Settings, hidden Beta (7 taps on version), near-neutral black Signature theme, Light default, toast/micro-animation layer, PRO_ENABLED=false.

## UNIFIED BUILD PLAN (approved via checklist)
Target: ONE merged full app ("Prizm v5 Unified") combining everything.
PUT IN: one-tap Google sync (drive.file engine + family-by-email), paste-key AI Boost sheet, first-review safety fixes (guess-limit, auto-lock manual, failed-save alerts, backup reminder, version sync).
CHANGE: apply the minimalist prizm-ducat design language across the whole app.
FROM DUCAT: gradient report bars; rebuild Analytics in Ducat style (big number + soft gradient bars) BUT keep most of Prizm's detail/clarity (category/account/member/income breakdowns, trends, period comparison).
Sequence: 1) merge sync+AI+safety into the design-revamped app  2) analytics Ducat rebuild  3) polish/QA.

## Also queued (functional, before design work)
- "One-tap Google" rewrite: replace Apps Script backend with direct Google Sheets API + drive.file scope. One tap → pick account → one consent → done. Removes: Apps Script API switch, unverified-program warning tab, "Anyone" public endpoint (and its password-guessing risk). Trade-off: family members each need Google sign-in; existing users need migration.
