# 📊 LIQUIDITY KPIs — METRICS TO CAPTURE BEFORE PHASE 2

**Entity:** OPTKAS1 LLC (Wyoming Series LLC, File# 2025-001184729)  
**Version:** 1.0  
**Date:** February 9, 2026  
**Purpose:** Define exactly what data must exist before engaging Phase 2 LPs. No data = no mandate.

> **Rule:** Phase 2 LPs (Keyrock, B2C, Amber LP-side) will ask for numbers.
> If you don't have these, the call ends. Capture them during Phase 1.

**Cross-references:**
- [LIQUIDITY_PROVIDER_STRATEGY.md](LIQUIDITY_PROVIDER_STRATEGY.md) — LP tiers + phasing
- [LP_INTRO_CALL_SCRIPTS.md](LP_INTRO_CALL_SCRIPTS.md) — What to say on calls
- [OUTREACH_EMAILS_JIMMY.md](OUTREACH_EMAILS_JIMMY.md) — Email templates

---

## TABLE OF CONTENTS

1. [Why KPIs Come Before Mandates](#why-kpis-come-before-mandates)
2. [Phase 1 KPIs (Days 0–30)](#phase-1-kpis-days-030)
3. [Phase 2 Gate Metrics (Day 30 Checkpoint)](#phase-2-gate-metrics-day-30-checkpoint)
4. [Phase 3 Gate Metrics (Day 60 Checkpoint)](#phase-3-gate-metrics-day-60-checkpoint)
5. [KPI Dashboard Template](#kpi-dashboard-template)
6. [What Each LP Tier Will Ask For](#what-each-lp-tier-will-ask-for)
7. [Red Flags That Delay Phase Advancement](#red-flags-that-delay-phase-advancement)

---

## WHY KPIs COME BEFORE MANDATES

```
╔══════════════════════════════════════════════════════════════════════════╗
║                                                                        ║
║  LPs don't take your word for it. They take your DATA for it.          ║
║                                                                        ║
║  Phase 1 exists to GENERATE the numbers Phase 2 LPs require.          ║
║  Phase 2 exists to GENERATE the numbers Phase 3 LPs require.          ║
║                                                                        ║
║  Skip the data → skip the LP. It's that simple.                        ║
║                                                                        ║
╚══════════════════════════════════════════════════════════════════════════╝
```

---

## PHASE 1 KPIs (Days 0–30)

Capture these during Phase 1 (dual-role firms: Wintermute, GSR, Cumberland).

### Settlement Metrics

| KPI | Definition | Target | How to Capture |
|:----|:-----------|:-------|:---------------|
| **Settlement Time** | Average time from trade initiation to final settlement | < 60 seconds on-chain | XRPL/Stellar transaction logs |
| **Settlement Success Rate** | % of settlements completed without manual intervention | > 99% | Transaction monitoring |
| **Failed Settlement Count** | Number of settlements requiring retry or manual fix | < 1 per week | Error logs |
| **Settlement Cost** | Average gas/fee per settlement | < $0.01 on XRPL | Fee tracking |

### Volume Metrics

| KPI | Definition | Target | How to Capture |
|:----|:-----------|:-------|:---------------|
| **Daily Transaction Count** | Number of distinct transactions per day | > 10/day by Day 30 | On-chain analytics |
| **Daily Notional Volume** | USD-equivalent volume per day | > $50K/day by Day 30 | Price × volume |
| **Average Transaction Size** | Mean notional per trade | $1K–$50K | Volume ÷ count |
| **Unique Counterparties** | Distinct wallets/entities transacting | > 3 by Day 30 | Address analysis |

### Behavior Metrics

| KPI | Definition | Target | How to Capture |
|:----|:-----------|:-------|:---------------|
| **Spread Stability** | Bid-ask spread variance over 24h | < 50bps variance | Order book snapshots |
| **Order Book Depth** | Total liquidity within 2% of mid | > $25K each side | Order book snapshots |
| **Wash Trade Ratio** | % of volume that is self-dealing | < 5% | Address clustering |
| **Organic Flow Ratio** | % of volume from non-MM sources | > 20% by Day 30 | MM attribution |

---

## PHASE 2 GATE METRICS (Day 30 Checkpoint)

**Do NOT engage Phase 2 LPs until ALL of these are met:**

```
┌─────────────────────────────────────────────────────────────────────┐
│                   PHASE 2 GATE — DAY 30 CHECKPOINT                 │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  □  Settlement success rate ≥ 99%                                  │
│  □  Daily volume ≥ $50K (7-day average)                            │
│  □  Spread variance < 50bps (7-day average)                        │
│  □  Unique counterparties ≥ 3                                      │
│  □  Zero material settlement failures in last 14 days              │
│  □  At least 1 credit close completed (Route A or 2.5)             │
│  □  Custody + insurance confirmed and active                       │
│                                                                     │
│  ALL BOXES CHECKED → Proceed to Phase 2 LP engagement              │
│  ANY BOX UNCHECKED → Stay in Phase 1. Do not advance.              │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

### Phase 2 Additional KPIs (Days 30–60)

| KPI | Definition | Target | Why Phase 2 LPs Care |
|:----|:-----------|:-------|:---------------------|
| **Weekly Volume Growth** | % increase in notional volume week-over-week | > 10% WoW | Shows organic adoption |
| **Pair Concentration** | % of volume in top pair vs. total | < 80% | Shows diversification |
| **LP Fill Rate** | % of LP quotes that result in trades | > 30% | Shows real flow, not dead quotes |
| **Inventory Turnover** | How often LP inventory cycles per day | > 2x/day | Shows capital efficiency |
| **Slippage** | Average execution vs. quoted price | < 25bps | Shows orderly execution |
| **Max Drawdown (LP)** | Largest unrealized loss on LP inventory | < 5% of inventory | Shows manageable risk |

---

## PHASE 3 GATE METRICS (Day 60 Checkpoint)

**Do NOT engage Phase 3 LPs (Jump, Virtu, Flow Traders) until ALL of these are met:**

```
┌─────────────────────────────────────────────────────────────────────┐
│                   PHASE 3 GATE — DAY 60 CHECKPOINT                 │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  □  All Phase 2 gate metrics still passing                         │
│  □  Daily volume ≥ $500K (14-day average)                          │
│  □  Weekly volume growth sustained ≥ 10% for 4+ weeks              │
│  □  Unique counterparties ≥ 10                                     │
│  □  LP fill rate ≥ 30% (14-day average)                            │
│  □  At least 2 active LP mandates (Phase 2 firms)                  │
│  □  Zero regulatory flags or compliance issues                     │
│  □  Inventory turnover ≥ 2x/day across all active LPs              │
│                                                                     │
│  ALL BOXES CHECKED → Proceed to Phase 3 LP engagement              │
│  ANY BOX UNCHECKED → Stay in Phase 2. Do not advance.              │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## KPI DASHBOARD TEMPLATE

Copy this and fill it weekly. Bring it to every LP conversation.

```
╔══════════════════════════════════════════════════════════════════════════╗
║                     OPTKAS1 — LIQUIDITY KPI DASHBOARD                  ║
║                     Week of: [DATE]                                    ║
╠══════════════════════════════════════════════════════════════════════════╣
║                                                                        ║
║  SETTLEMENT                                                            ║
║  ─────────                                                             ║
║  Success Rate:        [___]%     (target: >99%)                        ║
║  Avg. Time:           [___]s     (target: <60s)                        ║
║  Failed Settlements:  [___]      (target: <1/week)                     ║
║  Cost per Settle:     $[___]     (target: <$0.01)                      ║
║                                                                        ║
║  VOLUME                                                                ║
║  ──────                                                                ║
║  Daily Avg Volume:    $[___]     (P1: >$50K / P2: >$500K)             ║
║  Daily Txn Count:     [___]      (target: >10)                         ║
║  Avg Txn Size:        $[___]                                           ║
║  Unique Counterparties: [___]    (P1: >3 / P2: >10)                   ║
║                                                                        ║
║  BEHAVIOR                                                              ║
║  ────────                                                              ║
║  Spread Variance:     [___]bps   (target: <50bps)                      ║
║  Order Book Depth:    $[___]     (target: >$25K each side)             ║
║  Organic Flow:        [___]%     (target: >20%)                        ║
║  LP Fill Rate:        [___]%     (target: >30%)                        ║
║                                                                        ║
║  HEALTH                                                                ║
║  ──────                                                                ║
║  WoW Growth:          [___]%     (target: >10%)                        ║
║  Inventory Turnover:  [___]x     (target: >2x/day)                     ║
║  Max LP Drawdown:     [___]%     (target: <5%)                         ║
║  Compliance Flags:    [___]      (target: 0)                           ║
║                                                                        ║
║  PHASE STATUS:  Phase [1/2/3]    GATE: [PASS / FAIL]                   ║
║                                                                        ║
╚══════════════════════════════════════════════════════════════════════════╝
```

---

## WHAT EACH LP TIER WILL ASK FOR

### Tier 1 (Jump, Virtu, Flow Traders) — They'll ask:
- "Show me 60 days of volume data."
- "What's your daily notional and how fast is it growing?"
- "How many unique counterparties do you have?"
- "What does your order book look like at 2% depth?"
- "Have you had any settlement failures?"

**If you can't answer these, the call is over.**

### Tier 2 (Keyrock, B2C, Amber LP-side) — They'll ask:
- "What pairs are you running and what's the volume split?"
- "What fill rate are you seeing on existing LP quotes?"
- "What's the inventory turnover look like?"
- "Do you have any existing LP mandates we can reference?"

**If you can't answer these, they'll say "come back later."**

### Tier 3 / Dual-Role (Wintermute, GSR, Cumberland) — They'll ask:
- "What does the first week of trading look like?"
- "How tight do you want the spreads?"
- "What's your pause/kill-switch protocol?"
- "Are there any other MMs active?"

**These are the most pragmatic. They'll work with thin data, but want honesty.**

---

## RED FLAGS THAT DELAY PHASE ADVANCEMENT

| Red Flag | What It Means | Action |
|:---------|:-------------|:-------|
| Settlement success < 95% | Infrastructure not ready | Fix before any LP conversation |
| Wash trade ratio > 20% | Fake volume | Remove bad actors, rebuild organically |
| Spread variance > 100bps | Market is disorderly | Tighten MM parameters or reduce pairs |
| Zero organic flow after 14 days | No real demand | Pause LP expansion, focus on credit closes |
| LP drawdown > 10% | Inventory risk too high | Reduce position sizes, narrow spreads |
| Regulatory flag | Compliance breach | Full stop. Resolve before any outreach. |

---

*CONFIDENTIAL — OPTKAS1 LLC. Internal use only.*
