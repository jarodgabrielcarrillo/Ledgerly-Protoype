# Ledgerly Design System v1.0
### "The Modern Ledger" — fountain pen ink on warm paper, books that close with a satisfying click.

---

## 1. Vision & Mood

**The person:** a 19-year-old accountancy student at 9 PM, phone in one hand, dreading another drill app. Ledgerly should feel like sitting down at a beautiful desk, not logging into a portal.

**The feeling in one sentence:** the quiet satisfaction of a trial balance that ticks out, made tactile.

**Three governing words:**
- **Inked** — actions leave marks. Entries write themselves in, stamps land, lines rule themselves.
- **Equilibrium** — the entire product orbits one truth: debits equal credits. The UI makes balance *physical*.
- **Lamplight** — warm paper, cool ink, generous space. Serene, never sterile.

**What we reject:**
| Default | Replacement |
|---|---|
| Left sidebar + topbar shell | A single "spine" header; content lives on "the desk" |
| Flame-icon streak | "Closing streak" — days the books closed clean, stamped like an auditor's tick |
| Progress bars | The Balance Beam, stitch ribbons, the Cycle Dial |
| Gamified confetti | The "settle": beam levels, jade glow blooms, BALANCED stamp rotates in |
| Inter/Roboto on white | Fraunces + Schibsted Grotesk + Spline Sans Mono on warm ivory |

---

## 2. Color

### Light mode — "Daylight Desk" (default)
| Token | Hex | Role |
|---|---|---|
| `--paper` | #F6F1E4 | App background. Warm ivory, like ledger stock |
| `--paper-raised` | #FCFAF2 | Cards, panels (elevation 1) |
| `--paper-high` | #FFFEF9 | Dropdowns, receipts, inputs-on-focus (elevation 2) |
| `--paper-sunken` | #EFE8D6 | Input resting state, pressed surfaces (inset) |
| `--rule` | #E2D8BF | Standard borders / ruled lines |
| `--rule-soft` | #EAE2CD | Card borders, soft separation |
| `--rule-firm` | #CDBF9E | Emphasis rules, double-rule totals |
| `--ink` | #21303F | Primary text, primary buttons. Fountain-pen blue-black |
| `--ink-2` | #4C5B6D | Secondary text |
| `--ink-3` | #84909F | Metadata, labels |
| `--ink-4` | #B3BBC6 | Placeholders, disabled |
| `--jade` | #2E7C6A | Balance, success, primary positive action |
| `--jade-deep` | #235F52 | Hover, emphasis text |
| `--jade-wash` | #E3EEE6 | Success tints, selection |
| `--redink` | #B8432F | Errors and corrections ONLY. Red ink is sacred in accounting |
| `--redink-wash` | #F6E5E0 | Error field tints |
| `--brass` | #A0782B | Earned things: streaks, stamps, milestones |
| `--brass-wash` | #F2E8CE | Brass tints |

### Dark mode — "After Hours" (lamplight, not void)
Same hue family, inverted lightness, slightly desaturated semantics:
| Token | Hex |
|---|---|
| `--paper` | #14181F |
| `--paper-raised` | #1B212A |
| `--paper-high` | #232B36 |
| `--paper-sunken` | #10141A |
| `--rule` | #2B3440 / `--rule-soft` #242C37 / `--rule-firm` #3B4757 |
| `--ink` (text) | #E9E4D6 (warm parchment text on cool ground — the inversion of light mode) |
| `--ink-2` #B4AE9E · `--ink-3` #837F73 · `--ink-4` #565349 |
| `--jade` | #4DA08C · `--jade-wash` rgba(77,160,140,.14) |
| `--redink` | #D06A57 |
| `--brass` | #C49A4A |

Dark-mode rules: borders carry hierarchy (shadows vanish), elevation = +3–4% lightness per step, jade glow effects get ~40% more opacity since they read as lamplight.

**Color discipline:** one accent (jade) does the work. Brass appears only on earned moments. Red ink appears only when something is wrong. Max 3 non-neutral colors visible per screen.

---

## 3. Typography

| Role | Face | Why |
|---|---|---|
| Display / headings | **Fraunces** (variable, optical sizing) | A warm "wonky" serif with old-book DNA. Italic variants give Sage and narrative text a handwritten margin-note voice |
| UI / body | **Schibsted Grotesk** | Crisp, friendly grotesque. Distinct from the Inter default, holds up at 13–16px |
| Figures / data | **Spline Sans Mono** | Tabular numerals, soft terminals. Every monetary amount, date, code, and label uses it. `font-variant-numeric: tabular-nums` everywhere money appears |

### Scale (1.25 ratio, 16px base)
| Token | Size / weight / tracking | Use |
|---|---|---|
| `display-xl` | 46px Fraunces 500, -0.02em | Landing hero, greeting |
| `display-l` | 29px Fraunces 600, -0.015em | Card titles, scenario names |
| `display-m` | 21px Fraunces 600 | Section heads |
| `body` | 16px Schibsted 400, lh 1.5 | Default |
| `body-s` | 14px Schibsted 400/500 | Supporting text |
| `label` | 11px Spline Mono 500, +0.14em, uppercase | Panel labels, column heads |
| `figure-l` | 17px Spline Mono 600 | Totals |
| `figure` | 14px Spline Mono 400 | Line amounts |

Narrative and Sage text: Fraunces italic, `--ink-2`. Story text reads like a novel, never like a word problem.

---

## 4. Spacing, Radius, Depth, Motion, Icons

- **Spacing:** 4px base. Working multiples: 4 / 8 / 12 / 16 / 24 / 32 / 52. Card padding 32 (24 mobile). Section gaps 24.
- **Radius:** 8 inputs/chips · 12 buttons/tickets · 16 rail cards · 20 primary cards. Stamps and ticks get 5–9.
- **Depth strategy:** subtle layered warm shadows (`rgba(63,48,18,…)` never pure black) + 1px `--rule-soft` border on every raised surface. One strategy, everywhere. Shadows are sepia-warm so cards feel like paper on paper.
- **Motion:** 150–250ms micro-interactions, `cubic-bezier(.2,.7,.2,1)` deceleration. The Balance Beam alone gets 600ms with a 5% overshoot (the only "springy" element — it's a physical object). Page loads: one staggered rise (60ms increments). Honor `prefers-reduced-motion`.
- **Icons:** 1.6px-stroke line icons (Lucide-compatible), 14–24px, always paired with text on actions. The nib mark (pen nib with jade ink drop) is the logo glyph.

---

## 5. Signature Motifs

These five recur on every screen. They are the brand.

1. **The Balance Beam.** A literal beam on a fulcrum under every journal entry. Tilts toward the heavier side in real time as amounts are typed; levels and glows jade when Dr = Cr. The post button stays dim until the beam levels. Students *feel* the accounting equation.
2. **Double-rule totals.** Every total row uses the classic trial-balance ruling: single line above, double line below (`border-top: 1px solid ink; border-bottom: 3px double ink`). Used for section dividers and the page footer too. Accountants will recognize it instantly; everyone else just feels "finished-ness."
3. **Ink-in animation.** Posted entries, T-account postings, and feedback notes reveal left-to-right via `clip-path` with a brief jade wash, like wet ink drying. Nothing pops; everything *writes*.
4. **Stamps & stitches.** Earned states are rotated stamps (BALANCED, CLOSED, DAY 10) with a -2 to -6° tilt. Progress through a scenario is a "stitch ribbon" — the binding of the book filling in.
5. **Paper artifacts.** Source documents are receipts with torn edges (clip-path zigzag) and perforated ticket stubs (dashed rules + vertical stub text). The AI hands you *evidence*, not a paragraph of requirements.

6. **The settle & the splatter.** Delight is reserved for *earned* moments and stays in the ink metaphor: when an entry balances, the beam over-corrects and settles with an expanding jade ring; posting flicks a handful of ink droplets from the button. Hover play (seesawing library beams, straightening receipts, wiggling stamps, fanning tickets) invites touch without demanding attention. Copy rotates — beam captions, greeting lines, balance quips — so the desk never says the same thing twice. Never confetti, never badges, never sound.

**Sage**, the AI, is a jade orb (radial gradient sphere) with a Fraunces-italic voice. Sage never shows red Xs. Hints arrive blurred behind a "Reveal" veil so curiosity is a choice, not a spoiler.

---

## 6. Core Components

- **Buttons:** `btn-ink` (primary, ink fill), `btn-jade` (positive/post — and the Post button *becomes* jade only when the entry balances, a state change with meaning), `btn-ghost`. 13px×24px padding, 48px min height, scale(.97) on press.
- **Inputs:** rest on `--paper-sunken` (inset = "type here"), borderless until hover, focus = `--paper-high` + jade ring `0 0 0 3px rgba(46,124,106,.14)`. Amount inputs: mono, right-aligned, live thousands formatting.
- **Journal row:** grid `1fr 128px 128px 30px`. Credit lines auto-indent 34px (real bookkeeping convention — the UI teaches by convention). A line accepts debit OR credit; typing one clears the other.
- **T-account card:** Fraunces account name over a 2px ink underline, two columns split by a 2px ink center rule, mono figures, balance row beneath a single rule. New postings ink in bold then settle.
- **Receipt / ticket:** see motifs. Receipts rotate -0.6° so the desk feels inhabited.
- **Modals:** `--paper-high`, radius 20, rise+fade 220ms, backdrop `rgba(33,48,63,.32)` with 2px blur.
- **Chips:** pill, mono 12px, washed background + 25%-opacity border of their hue (jade = balanced, brass = streak, red = off-balance).

---

## 7. Screens

### 7.1 Landing *(built: ledgerly-landing.html)*
- **Layout:** centered single column, no nav clutter (wordmark + Sign in only). Hero headline in Fraunces: *"Every business has a story. Learn to read it in numbers."* Below it, a **live typing demo**: an AI-generated scenario writes itself in italic serif ("A flower stall in Baguio, the morning before Valentine's…"), then a journal entry inks in beneath it and the Balance Beam settles. The product demos itself in 8 seconds, on loop, no video player.
- **Hierarchy:** headline → living demo → single jade CTA ("Open your first set of books") → three quiet proof rows (double-rule separated): infinite scenarios, real cycle coverage, Sage feedback.
- **Curiosity/serenity:** the only motion is the self-writing demo; everything else is still paper.
- **Mobile:** demo stacks under headline; beam shrinks to 180px; CTA goes full-width sticky above the fold's end.

### 7.2 Dashboard — "The Desk" *(built: ledgerly-dashboard.html)*
- **Layout:** spine header (wordmark · The Desk / Scenarios / Progress · streak chip · avatar). Greeting block with a personal, scenario-aware line ("Driftwood Coffee still owes you an entry"). Row 1: **case file** (active scenario, manila-folder tab, stitch ribbon, double-rule meta strip, Open the books) + **closing streak** (big serif number, 7 tick cells, today's cell breathes with a brass dashed border). Row 2: **ticket deck** (three fanned scenario tickets that splay on hover + "Deal me a fresh business"), **cycle dial** (SVG arc draws in on load, step list with brass "you are here" dot), **note from Sage** (margin-note quote about yesterday's mistake).
- **Key interactions:** cards rise in staggered; case file lifts 3px on hover; deck fans; dial arc animates once.
- **Curiosity:** the deck's visible ticket titles tease what's inside; Sage's note references a *specific* past entry. **Serenity:** one accent color, ruled-paper background lines at 32px rhythm, no badges screaming.
- **Mobile:** rows collapse to single column in priority order (case file → streak → deck → dial → Sage); nav wraps to a scrollable pill row.

### 7.3 Scenario Generator — "The Deal" *(built: ledgerly-generator.html)*
- **Layout:** full-screen paper void. Three input dials only: difficulty (Beginner / Core / Stretch as ticket stubs), focus (cycle stage chips), vibe (optional free text: "make it a sari-sari store"). One button: **Deal me a business**.
- **The magic moment:** screen dims to lamplight; a blank folder slides to center; the scenario *types itself* in Fraunces italic — business name first (large, like a title page), then the opening paragraph, then meta stamps land one by one (INDUSTRY: F&B, DAYS: 7, ACCOUNTS: 14) with stamp-rotate-in. Total ~4s, skippable with a tap. Then the folder's tab gains the scenario name and a single jade "Open Day 1."
- **Why it works:** generation latency becomes theater. The typing IS the loading state.
- **Mobile:** identical; the folder is already a portrait shape.

### 7.4 Active Workspace *(built: ledgerly-workspace.html — the heart)*
- **Layout:** three desk zones, no sidebar chrome. **Left — The Story** (sticky): the narrative beat in serif, then the source document (torn receipt with line items, double-rule total, red-ink terms line), transaction counter. **Center — The Journal:** entry card (title, GJ number, column-ruled rows, credit indent, add-line, double-rule totals, Balance Beam + Post), then the day's posted ledger beneath with BALANCED stamps. **Right — Live Ledger** (sticky): mini T-accounts that receive postings in real time, and Sage with a blurred hint veil.
- **The loop:** read the story → inspect the evidence → write the entry → watch the beam tilt with every keystroke → it levels, card border warms jade, Post turns jade → post → entry inks into the ledger AND ripples into the T-accounts → next transaction slides in.
- **Micro-interactions:** beam tilt (600ms, slight overshoot), totals turn jade when even, "leaning to the debit side · off by ₱X" caption in italic, posted entries clip-path ink-in, T-account figures bold-then-settle, hint blur dissolves over 500ms.
- **Serenity:** errors never flash red mid-typing — imbalance is just a tilted beam and a quiet caption. Red ink waits for the review screen. **Curiosity:** the hint veil, the story's unanswered question ("which account did Driftwood promise?" as the input placeholder).
- **Mobile:** story collapses to a swipe-down sheet pinned as a top strip ("Day 3 · Invoice #1042 · ₱12,500 ▾"); journal takes the screen; T-accounts and Sage move below; beam zone stacks vertically with Post full-width.

### 7.5 AI Feedback — "The Review" *(built: ledgerly-review.html)*
- **Layout:** the posted journal page reproduced at center, but now annotated like a marked manuscript. Correct entries get jade tick stamps in the margin. The flawed entry gets a hand-drawn-style underline (SVG squiggle path, draws in) and a **margin note** from Sage in Fraunces italic, connected by a thin leader line — exactly like a professor's marginalia, never a modal.
- **Note anatomy:** (1) what you saw — "You debited Supplies ₱12,500" (2) the reframe — "Beans are what Driftwood *sells*. Things a business sells are Inventory; things it consumes are Supplies." (3) the fix, shown as a small correcting entry that inks in (4) one-line principle to keep, savable to a personal "Field Notes" book.
- **Tone rules:** Sage names the reasoning, not the failure. Red ink appears only on the specific wrong account name, struck through with the correction written above it — a real bookkeeping correction, which is itself a lesson (no erasing in accounting).
- **Ending:** if the period balanced, the page receives a large rotated CLOSED stamp with a soft thump animation, and the streak tick fills on the spot.
- **Mobile:** margin notes become tap-to-expand jade dots anchored to each line.

### 7.6 Progress & Insights — "The Folio" *(built: ledgerly-progress.html)*
- **Layout:** styled as the student's own annual report. Top: a **personal balance sheet of skills** — "Assets" (mastered: journalizing 92%, posting 88%…) vs "Liabilities" (open gaps: adjusting entries 41%) with the double-rule total reading *Equity: your judgment*. It's a data viz that could only exist in this product.
- **Below:** the Cycle Dial, full size, each segment tappable to drill into attempts; a calendar of brass-stamped closing days; a shelf of completed scenario spines (each finished business becomes a small book spine on a shelf — collection mechanic without badges); Field Notes (saved principles from reviews, in Sage's italic).
- **Curiosity:** tapping a book spine reopens that business's final statements. **Serenity:** no leaderboards, no comparison to others; the only competitor is last month's folio.
- **Mobile:** balance-sheet-of-skills stacks Assets above Liabilities; shelf scrolls horizontally.

### 7.7 Library — "The Shelves" *(built: ledgerly-library.html)*
- **Layout:** spine nav → header → **normal-balance primer** (two mini beams, one tilted each way, with a plain-language explainer: "every account has a side where it naturally rests") → filter chips by element type + search → accounts grouped into **shelves** (Assets / Liabilities / Equity / Revenue / Expenses), each shelf headed by a double-rule line and a one-line "lean debit/credit" reminder.
- **Account card anatomy (the index card):** name + mini Balance Beam permanently tilted to its normal side (the signature motif doing reference duty), one-line meaning, "Normal balance: DEBIT/CREDIT" label. Tap to expand: *Grows with / Shrinks with* rule pair (grow side in jade), a Fraunces-italic **"what it means for the business"** passage, and a **"Seen in the wild"** example entry drawn from Driftwood Coffee, so reference connects back to the scenario the student is living in.
- **Contra accounts** (Accumulated Depreciation, Owner's Drawings) carry a rotated red-ink CONTRA stamp and a beam tilted against their shelf, a visual lesson in itself.
- **Curiosity:** the beams differ card to card; spotting the two "wrong-way" tilts invites the contra question before any text explains it. **Serenity:** no quizzing here, no scores; the library is the one room with nothing to get wrong.
- **Mobile:** chips wrap, search goes full width, grid collapses to one column, cards stay tap-to-expand.



- Sage speaks in first person, short sentences, italic serif. Encouraging through specificity, never through exclamation marks.
- System copy uses the world's vocabulary: "Open the books," "Post entry," "Close the period," "The desk," "Folio."
- Numbers always carry currency and tabular alignment. Money is never decoration.

---

## 9. Tailwind port (tokens)

```js
// tailwind.config.js
export default {
  theme: {
    extend: {
      colors: {
        paper: {DEFAULT:'#F6F1E4', raised:'#FCFAF2', high:'#FFFEF9', sunken:'#EFE8D6'},
        rule:  {DEFAULT:'#E2D8BF', soft:'#EAE2CD', firm:'#CDBF9E'},
        ink:   {DEFAULT:'#21303F', 2:'#4C5B6D', 3:'#84909F', 4:'#B3BBC6'},
        jade:  {DEFAULT:'#2E7C6A', deep:'#235F52', wash:'#E3EEE6'},
        redink:{DEFAULT:'#B8432F', wash:'#F6E5E0'},
        brass: {DEFAULT:'#A0782B', wash:'#F2E8CE'},
      },
      fontFamily: {
        display: ['Fraunces','Georgia','serif'],
        body: ['"Schibsted Grotesk"','sans-serif'],
        figures: ['"Spline Sans Mono"','monospace'],
      },
      borderRadius: {s:'8px', m:'12px', l:'16px', xl:'20px'},
      boxShadow: {
        1:'0 1px 2px rgba(63,48,18,.05),0 2px 8px rgba(63,48,18,.05)',
        2:'0 2px 4px rgba(63,48,18,.06),0 10px 28px rgba(63,48,18,.09)',
        3:'0 4px 8px rgba(63,48,18,.07),0 22px 48px rgba(63,48,18,.12)',
      },
      transitionTimingFunction: {settle:'cubic-bezier(.2,.7,.2,1)'},
    }
  }
}
```

Custom utilities to add: `.rule-total` (single-over-double border), `.ink-in` (clip-path keyframe), `.credit-indent` (pl-[34px]).
