# MARKET-ANALYSIS.md — Skill: Market & Financial Analysis

This skill applies the universal Layer 3/4 data protocol (defined in REASONING.md) to financial and market analysis tasks specifically.

Activate when the user requests:
- Market analysis, price outlook, commodity report
- "Current" / "this week" / "next week" views on any asset
- Technical analysis, trend analysis
- Macro factor impact on an asset class
- Gold, silver, oil, FX, crypto, equity index analysis

---

## Why this exists

Market prices are the clearest example of Layer 3 data: specific, numerical, and changes continuously. Training data contains prices — but those prices are frozen at the training cutoff and carry no date. A gold price from training memory is not a gold price. It is an undated historical figure presented without disclosure. That is a professional failure.

This skill operationalises the universal data rule for market contexts.

---

## Phase 1 — Announce before searching

Tell the user what you're doing before you start:
> "Running a live data sweep for [asset] before drafting. This will take a moment."

This confirms the agent is working correctly, not drawing from memory.

---

## Phase 2 — Live data sweep (complete before any drafting)

**2A — Spot price anchor (today)**
```
Search: "[asset] spot price today"
Search: "[asset] price [current date]"
Fetch:  most credible result (Reuters, Bloomberg, Kitco for gold)
Record: the price AND the exact date/time of the quote
```

**2B — Recent price action (last 2–4 weeks)**
```
Search: "[asset] price [current month] [year]"
Search: "[asset] weekly performance"
Goal:   trend direction, trading range, key levels
```

**2C — Macro drivers**
```
Search: "Fed interest rate decision latest"
Search: "US dollar index latest"
Search: "[asset] market drivers [current month]"
Search: relevant macro event (CPI, NFP, geopolitical)
Fetch:  pages with key data points in snippets
```

**2D — Sentiment and positioning**
```
Search: "[asset] COT report latest"
Search: "[asset] ETF flows latest"
Search: "[asset] options positioning" or "[asset] put call ratio"
```

**2E — Forward signals**
```
Search: "[asset] outlook [current month] [year]"
Search: "[asset] technical analysis [current month]"
Search: "[asset] forecast next week"
Fetch:  2–3 most substantive pages
```

**2F — Data age verification**
For every figure you intend to use:
- Source name confirmed?
- Publication date confirmed?
- Retrieved in this session (not from training)?

Fail any check → search for the dated version or mark as a gap.

---

## Phase 3 — Mandatory report header

First thing in the report:
```
Report:     [Asset] Market Analysis
Coverage:   [current week] and [next week]
Data as of: [date and time of most recent data point]
Sources:    [sources searched this session]
Gaps:       [any figure not confirmed from live search — or "None"]
Note:       All market data from live web search. Training memory not used
            for any price, rate, or market level.
```

---

## Phase 4 — Write the report

**Every price, rate, or level cited must include its date:**
> "Gold spot at $X,XXX/oz (Kitco, [date])"

**Every forward-looking statement must be framed as a view:**
> "The technical picture suggests..." / "Analyst consensus leans toward..."

**Standard structure:**
1. Spot price (sourced, dated)
2. Recent price action
3. Key drivers (USD, rates, macro, geopolitical)
4. Technical picture (support/resistance, trend, momentum)
5. Current week outlook
6. Next week outlook
7. Risks to the view
8. Data gaps / caveats

**Prohibited patterns:**
- ❌ Any price with no date — stale data leak
- ❌ "Markets have been range-bound" with no time reference
- ❌ "The Fed is expected to..." without citing a specific recent source
- ❌ "Based on historical patterns" as a substitute for current data

---

## Phase 5 — Self-review checklist

- [ ] Every figure has a source and date
- [ ] No figure from training memory alone
- [ ] Data header present
- [ ] Forward views framed as views, not facts
- [ ] Risks to the view included
- [ ] Data gaps disclosed (or confirmed none)
- [ ] Report answers what was actually asked

---

## Phase 6 — Confidence statement

End with:
> **Confidence: [High / Medium / Low]**
> Reason: [e.g. "Full data coverage — high" or "Positioning data unavailable — medium"]

---

## Gold-specific search terms

```
Price:        "gold spot price today" / "XAU/USD price today"
Action:       "gold price this week" / "gold price [month] [year]"
Macro:        "Fed rate decision gold" / "US dollar index today" / "real yields gold"
Sentiment:    "gold COT report latest" / "GLD ETF flows" / "gold futures positioning"
Outlook:      "gold outlook [month] [year]" / "gold technical analysis [month]"
Geopolitical: "gold safe haven demand [current event]"
```
