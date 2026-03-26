# MARKET-ANALYSIS.md — Skill: Financial & Market Analysis Reports

Read this file whenever the user requests any of the following:
- Market analysis, price outlook, or commodity report
- "Current" or "this week" / "next week" price views
- Technical analysis, trend analysis, or chart review
- Macro factor impact on any asset class
- Gold, silver, oil, FX, crypto, equity index analysis

**This skill overrides the default 5-step loop for report-type outputs.**
Follow the workflow below in full. Do not shortcut it.

---

## Why this skill exists

The model's training data contains market prices — but those prices are frozen at the training cutoff, which may be months or years in the past. A gold price from training data is not "the gold price." It is a historical figure with no disclosed date. Using it without disclosure is a professional failure.

This skill enforces a live-data-first workflow that makes stale data physically impossible to slip into a report undetected.

---

## The 6-Phase Report Workflow

### Phase 1 — Acknowledge the task and state intent

Before searching, tell the user what you're about to do:

> "Starting a live data sweep for [asset] before drafting. This will take a moment."

This sets expectations and signals that the agent is working correctly — not hallucinating from memory.

---

### Phase 2 — Live data sweep (mandatory, before any drafting)

Run ALL of the following searches. Do not skip any. Do not start drafting until Phase 2 is complete.

**2A — Spot price anchor (TODAY)**
```
Search: "[asset] spot price today"
Search: "[asset] price [current date]"
Fetch: the most credible result page (Reuters, Bloomberg, Kitco for gold, etc.)
Record: the price AND the exact date/time of the quote
```

**2B — Recent price action (last 2–4 weeks)**
```
Search: "[asset] price [current month] [year]"
Search: "[asset] weekly performance"
Goal: identify trend direction, trading range, key levels broken or held
```

**2C — Macro drivers (what's moving it)**
```
Search: "Fed interest rate decision latest" (always relevant for gold/commodities)
Search: "US dollar index latest"
Search: "[asset] market drivers [current month]"
Search: "[relevant macro event] latest" — e.g. CPI, NFP, geopolitical event
Fetch: any result page where the snippet contains a key data point
```

**2D — Sentiment and positioning**
```
Search: "[asset] COT report latest" (Commitment of Traders)
Search: "[asset] ETF flows latest" (e.g. GLD flows for gold)
Search: "[asset] options positioning" or "[asset] put call ratio"
```

**2E — Forward signals (next 1–2 weeks)**
```
Search: "[asset] outlook [current month] [year]"
Search: "[asset] technical analysis [current month]"
Search: "[asset] forecast next week"
Fetch: the 2–3 most substantive pages from these results
```

**2F — Data age verification**

Before moving to Phase 3, list every data point you intend to use and confirm:
- Source name
- Publication date
- Whether it was retrieved in this session via search (not from training memory)

If any data point fails this check: either search for the current figure, or mark it as a gap.

---

### Phase 3 — Structure the report before writing it

Decide the report structure before writing prose. Standard structure:

```
1. Data header (price, date, sources)
2. Current situation (what the price is and how it got here)
3. Key drivers (what's moving it right now)
4. Technical picture (levels, trend, momentum)
5. Macro context (rates, USD, risk sentiment, geopolitics)
6. Outlook — current week
7. Outlook — next week
8. Risks to the view (what could invalidate the call)
9. Data gaps / caveats (if any live data was unavailable)
```

Adjust structure to fit the user's specific request. If they only asked for "next week outlook," sections 6–8 are the core and others are context.

---

### Phase 4 — Write the report

**Mandatory header (first thing in the report):**
```
Report: [Asset] Market Analysis
Coverage: [current week dates] and [next week dates]
Data as of: [date and time of most recent data point]
Sources: [list sources searched this session]
Note: All market data retrieved via live web search in this session.
        Training knowledge not used for any price, rate, or market level.
```

**Writing rules:**
- Every price, level, or rate cited must include its date: "Gold spot at $X,XXX/oz (as of [date])"
- Every forward-looking statement must be framed as a view, not a fact: "The technical picture suggests...", "Analyst consensus leans toward..."
- Distinguish between what the data shows (factual) and what it implies (analytical)
- If two sources give conflicting figures, state both and note the discrepancy
- Do not soften a bearish view to seem positive, or a bullish view to seem balanced. Report what the data shows.

**Prohibited patterns:**
- ❌ "Gold is trading around $1,800" with no date — this is a training-data leak
- ❌ "Markets have been range-bound" with no time reference
- ❌ "The Fed is expected to..." without citing a specific recent statement or market pricing
- ❌ Conclusions stated before the data that supports them is presented
- ❌ "Based on historical patterns" as a substitute for current data

---

### Phase 5 — Self-review before delivering

Before sending the report, run this checklist:

- [ ] Every price/level has a source and a date attached
- [ ] No figure came from training memory alone — all verified by session search
- [ ] The mandatory data header is present at the top
- [ ] Forward views are framed as views, not facts
- [ ] Data gaps are explicitly disclosed (if any)
- [ ] The report answers what the user actually asked (current week + next week)
- [ ] Risks to the view are included — a report with no downside scenarios is not credible

---

### Phase 6 — Deliver with a confidence statement

End the report with a brief confidence note:

> **Confidence level:** [High / Medium / Low]
> **Reason:** [e.g. "Strong live data coverage across price, macro, and positioning. High confidence." or "Sentiment/COT data unavailable from live search — positioning picture is incomplete. Medium confidence."]

This is not a disclaimer. It is a professional signal that tells the user how much weight to put on the view.

---

## Gold-Specific Search Terms (reference)

For spot gold / XAU/USD analysis, these search terms are consistently high-yield:

```
Price anchor:      "gold spot price today"
                   "XAU/USD price today"
Price action:      "gold price this week"
                   "gold price [month] [year]"
Macro drivers:     "Fed rate decision gold impact"
                   "US dollar index today"
                   "real yields gold"
                   "DXY gold correlation"
Sentiment:         "gold COT report latest"
                   "GLD ETF flows"
                   "gold futures positioning"
Outlook:           "gold outlook [month] [year]"
                   "gold technical analysis [month]"
                   "gold price forecast next week"
Geopolitical:      "gold safe haven demand [current event]"
```

---

## What a well-formed gold report looks like (structure example)

```
=== GOLD MARKET ANALYSIS ===
Report: XAU/USD — Current & Next Week Outlook
Data as of: [exact date and time]
Sources: Kitco, Reuters, CME FedWatch, CFTC COT report
Note: All figures from live search conducted [today's date].

SPOT PRICE
Gold is currently trading at $X,XXX/oz (Kitco, [date]), up/down X.X%
from last week's close of $X,XXX/oz.

RECENT PRICE ACTION
[2–3 sentences on the past 2 weeks: range, key moves, levels held or broken]

KEY DRIVERS
[USD]: The DXY is at [level] ([source, date])...
[Rates]: 10-year real yield at [level]...
[Macro event]: [Fed/CPI/NFP result and market reaction]...
[Geopolitical]: [current relevant factor if applicable]...

TECHNICAL PICTURE
[Support/resistance, trend, momentum indicator if found in search]

CURRENT WEEK OUTLOOK
[View + reasoning + key level to watch]

NEXT WEEK OUTLOOK
[View + upcoming events that could move price + scenarios]

RISKS TO THE VIEW
[Bull case risk] / [Bear case risk]

DATA GAPS
[Anything you couldn't confirm from live search — or "None" if fully covered]

CONFIDENCE: [High/Medium/Low] — [one sentence reason]
=========================
```

---

## Trigger phrases for this skill

Activate this skill whenever the user says any of:
- "market analysis", "price analysis", "technical analysis"
- "current price", "today's price", "where is [asset] trading"
- "this week / next week" + any asset name
- "outlook", "forecast", "price target"
- "gold", "XAU", "silver", "oil", "crude", "FX", "[currency pair]"
- "commodity report", "market report", "trading view"
