# 🛡️ AMM GUARDRAILS — TOKEN PAIR RESTRICTIONS

**Entity:** OPTKAS1 LLC (Wyoming Series LLC, File# 2025-001184729)  
**Version:** 1.0  
**Date:** February 9, 2026  
**Purpose:** Define which token pairs must NEVER have early AMMs, which can have controlled AMMs, and when.

> **Core principle:** AMMs are permanent, public, and unforgiving.
> Once you deploy one, you can't take it back without reputation damage.
> Get this wrong and every LP labels you "retail project" forever.

**Cross-references:**
- [LIQUIDITY_PROVIDER_STRATEGY.md](LIQUIDITY_PROVIDER_STRATEGY.md) — LP tiers + phasing
- [LIQUIDITY_KPIs.md](LIQUIDITY_KPIs.md) — Gate metrics that must pass before AMM consideration
- [LP_INTRO_CALL_SCRIPTS.md](LP_INTRO_CALL_SCRIPTS.md) — What to say (and not say) about AMMs

---

## TABLE OF CONTENTS

1. [The AMM Danger Zone](#the-amm-danger-zone)
2. [Pair Classification Matrix](#pair-classification-matrix)
3. [NEVER-EARLY Pairs (Red List)](#never-early-pairs-red-list)
4. [CONTROLLED Pairs (Yellow List)](#controlled-pairs-yellow-list)
5. [SAFE Pairs (Green List)](#safe-pairs-green-list)
6. [AMM Deployment Decision Tree](#amm-deployment-decision-tree)
7. [AMM Parameter Guardrails](#amm-parameter-guardrails)
8. [What Goes Wrong Without This](#what-goes-wrong-without-this)

---

## THE AMM DANGER ZONE

```
╔══════════════════════════════════════════════════════════════════════════╗
║                                                                        ║
║  AMMs are NOT free liquidity.                                          ║
║  AMMs are PERMANENT PUBLIC COMMITMENTS.                                ║
║                                                                        ║
║  A bad AMM:                                                            ║
║  • Creates arb opportunities that drain your treasury                  ║
║  • Signals "retail project" to every institutional LP                  ║
║  • Can't be removed without looking like a rug                         ║
║  • Generates wash volume that poisons your KPI data                    ║
║  • Attracts bots, not institutions                                     ║
║                                                                        ║
║  Rule: If in doubt, DON'T deploy the AMM.                              ║
║  Use OTC / RFQ flow instead. Always.                                   ║
║                                                                        ║
╚══════════════════════════════════════════════════════════════════════════╝
```

---

## PAIR CLASSIFICATION MATRIX

Every possible pair falls into one of three categories:

| Classification | Meaning | AMM Allowed? | When? |
|:---------------|:--------|:-------------|:------|
| 🔴 **RED** (NEVER-EARLY) | Deploying this AMM early will cause structural damage | **NO** until Phase 3+ gate passes | Minimum 90 days + explicit LP approval |
| 🟡 **YELLOW** (CONTROLLED) | Can exist under strict parameters | **YES** with guardrails | After Phase 2 gate + KPI dashboard green |
| 🟢 **GREEN** (SAFE) | Low-risk, infrastructure-grade | **YES** | After Phase 1 settlement proves stable |

---

## NEVER-EARLY PAIRS (Red List)

These pairs must **NEVER** have public AMMs in Phase 1 or Phase 2.

### 🔴 GEMVLT / USDC

| Field | Detail |
|:------|:-------|
| **Why it's red** | GEMVLT represents $430M in physical gems. A public AMM creates a price discovery mechanism for an illiquid physical asset. The "price" on the AMM will NOT reflect real gem value — it'll reflect speculative trading. |
| **What goes wrong** | Arb bots trade GEMVLT below gem value → "the gems are worth less than claimed" narrative. Or above → "pump" narrative. Both are fatal. |
| **Alternative** | OTC / RFQ only. Institutional counterparties. No public order book. |
| **When it can exist** | Phase 3+ ONLY, after: (a) at least 2 credit closes, (b) active LP mandates, (c) explicit written approval from counsel |

### 🔴 GEMVLT / XRP

| Field | Detail |
|:------|:-------|
| **Why it's red** | Correlates gem-backed asset to XRP price. If XRP drops 30%, GEMVLT "drops" 30% on the AMM — but the gems haven't moved. Institutional LPs will see this and walk. |
| **What goes wrong** | Creates false correlation between physical collateral and crypto market. Destroys the "uncorrelated asset" narrative that makes the whole system credible. |
| **Alternative** | Never pair GEMVLT directly with a volatile crypto. Use stablecoin intermediary always. |
| **When it can exist** | Potentially never. Evaluate only after 6+ months of stable stablecoin pair data. |

### 🔴 Any RWA Token / Meme Token

| Field | Detail |
|:------|:-------|
| **Why it's red** | Self-explanatory. Pairing a $5.44B collateral-backed asset with a meme token is instant institutional death. |
| **What goes wrong** | One screenshot of "GEMVLT/PEPE" on an AMM = every LP conversation canceled. |
| **Alternative** | Don't even think about it. |
| **When it can exist** | Never. |

### 🔴 Any Token / Any Token (Without LP Mandate)

| Field | Detail |
|:------|:-------|
| **Why it's red** | An AMM without an LP behind it is a thin, exploitable pool. Arb bots will drain it. The "volume" will be 100% wash. Your KPI data is poisoned. |
| **What goes wrong** | You show Phase 2 LPs your "volume numbers" and they immediately see it's all bot arb on a thin pool. Call ends. |
| **Alternative** | No AMM without at least one LP mandate in place for that specific pair. |
| **When it can exist** | Only after an LP has agreed to provide depth for that pair. |

---

## CONTROLLED PAIRS (Yellow List)

These pairs can exist with strict parameter controls after Phase 2 gate.

### 🟡 RWA-Stablecoin / USDC

| Field | Detail |
|:------|:-------|
| **When allowed** | After Phase 2 gate passes (Day 30+) |
| **Required guardrails** | Concentrated liquidity (±1% range), minimum $50K depth each side, active LP mandate, kill-switch enabled |
| **Purpose** | Allow institutional counterparties to settle RWA positions via stablecoin |
| **Risk** | Moderate — but controllable with tight ranges and active MM |

### 🟡 RWA-Stablecoin / USDT

| Field | Detail |
|:------|:-------|
| **When allowed** | After Phase 2 gate passes (Day 30+) |
| **Required guardrails** | Same as USDC pair above. Both can run simultaneously. |
| **Purpose** | USDT preference for some counterparties (especially Asian desks) |
| **Risk** | Same as USDC. Monitor for divergence between USDC and USDT pairs. |

### 🟡 USDC / USDT (Platform Settlement)

| Field | Detail |
|:------|:-------|
| **When allowed** | After Phase 1 settlement proves stable (Day 14+) |
| **Required guardrails** | Tight range (±0.1%), deep liquidity, standard stablecoin AMM parameters |
| **Purpose** | Allow counterparties to swap between stablecoins on-platform |
| **Risk** | Low — this is infrastructure. But still needs active LP to prevent arb drain. |

---

## SAFE PAIRS (Green List)

These pairs are infrastructure-grade and can deploy early with minimal risk.

### 🟢 USDC / USD (On-Ramp/Off-Ramp)

| Field | Detail |
|:------|:-------|
| **When allowed** | Day 0 — this is infrastructure |
| **Purpose** | Fiat on-ramp/off-ramp for institutional counterparties |
| **Risk** | Minimal — standard payment rail |
| **Notes** | Not technically an AMM — more of a payment gateway. But classify it here for completeness. |

### 🟢 USDT / USD (On-Ramp/Off-Ramp)

| Field | Detail |
|:------|:-------|
| **When allowed** | Day 0 |
| **Purpose** | Same as above, USDT variant |
| **Risk** | Minimal |

---

## AMM DEPLOYMENT DECISION TREE

Before deploying ANY AMM, walk through this:

```
                    ┌──────────────────────────────────┐
                    │   SHOULD WE DEPLOY THIS AMM?     │
                    └───────────────┬──────────────────┘
                                    │
                         ┌──────────▼──────────┐
                         │  Is the pair on the  │
                         │  RED LIST?           │
                         └──────────┬──────────┘
                                    │
                          YES ◄─────┼─────► NO
                           │                 │
                    ┌──────▼──────┐  ┌───────▼───────┐
                    │             │  │  Has Phase 2   │
                    │   STOP.     │  │  gate passed?  │
                    │   NO AMM.   │  │                │
                    │             │  └───────┬───────┘
                    └─────────────┘          │
                                   YES ◄────┼────► NO
                                    │                │
                             ┌──────▼──────┐  ┌─────▼──────┐
                             │  Is there   │  │            │
                             │  an active  │  │  WAIT.     │
                             │  LP mandate │  │  Phase 1   │
                             │  for this   │  │  only.     │
                             │  pair?      │  │            │
                             └──────┬──────┘  └────────────┘
                                    │
                          YES ◄─────┼─────► NO
                           │                 │
                    ┌──────▼──────┐  ┌───────▼───────┐
                    │  Deploy     │  │               │
                    │  with       │  │  NO AMM       │
                    │  guardrails │  │  without LP.  │
                    │  (see       │  │  Use OTC/RFQ. │
                    │  below)     │  │               │
                    └─────────────┘  └───────────────┘
```

---

## AMM PARAMETER GUARDRAILS

If you pass the decision tree and deploy an AMM, use these parameters:

### Concentration Range

| Pair Type | Range | Rationale |
|:----------|:------|:----------|
| RWA / Stablecoin | ±1% of target price | RWA value shouldn't move much. Tight range prevents arb. |
| Stablecoin / Stablecoin | ±0.1% | These are pegged. Any wider = free money for arb bots. |
| NEVER wider than ±5% | — | If you need ±5%, you don't have enough LP support. Don't deploy. |

### Minimum Depth

| Pair Type | Minimum Each Side | Rationale |
|:----------|:------------------|:----------|
| RWA / Stablecoin | $50,000 | Below this, a single trade moves the price. Not credible. |
| Stablecoin / Stablecoin | $100,000 | Standard institutional threshold. |

### Kill-Switch Protocol

```
┌─────────────────────────────────────────────────────────────────────┐
│                     AMM KILL-SWITCH TRIGGERS                        │
├─────────────────────────────────────────────────────────────────────┤
│                                                                     │
│  AUTOMATIC PAUSE if any of the following occur:                     │
│                                                                     │
│  □  Price deviates > 5% from reference in < 1 hour                 │
│  □  Volume spikes > 10x daily average in < 1 hour                  │
│  □  LP inventory drops below minimum depth                         │
│  □  Settlement failure rate exceeds 1%                              │
│  □  Wash trade ratio exceeds 30%                                   │
│  □  Regulatory inquiry received                                     │
│                                                                     │
│  ON PAUSE:                                                          │
│  1. Halt new trades                                                │
│  2. Allow existing settlements to complete                         │
│  3. Notify active LPs                                              │
│  4. Root cause analysis within 24 hours                            │
│  5. Resume only after RCA complete + fix verified                  │
│                                                                     │
└─────────────────────────────────────────────────────────────────────┘
```

---

## WHAT GOES WRONG WITHOUT THIS

### Scenario 1: GEMVLT/XRP AMM launches in Phase 1

```
Day 1:  GEMVLT trades at $4.20 (pegged to gem value)
Day 3:  XRP drops 25% in broader market
Day 3:  GEMVLT/XRP AMM shows GEMVLT "down 25%"
Day 3:  Screenshot circulates: "OPTKAS gem token crashed 25%"
Day 4:  Galaxy Digital cancels lending call
Day 5:  GSR emails: "We're pausing LP discussions"
Day 7:  Project labeled "retail scam" on CT

Result: $0 raised. Reputation destroyed. Gems are fine. Narrative isn't.
```

### Scenario 2: Thin USDC AMM with no LP mandate

```
Day 1:  $10K depth each side
Day 2:  Arb bot trades $5K, moves price 8%
Day 2:  Another bot arbs it back. $200 in fees generated.
Day 5:  "Volume" shows $50K/day — all bots
Day 14: Show data to Keyrock
Day 14: Keyrock: "This is 100% bot arb. There's no real flow."
Day 14: Call ends. Keyrock tells B2C. B2C tells Amber.

Result: Phase 2 LP pipeline dead. Data is poisoned. Start over.
```

### Scenario 3: Correct approach (what we're doing)

```
Day 1:  OTC/RFQ only. No public AMM.
Day 14: Phase 1 LPs provide thin controlled books
Day 30: Real data exists. Phase 2 gate passes.
Day 45: Controlled USDC AMM with Keyrock mandate. $50K+ depth.
Day 60: Phase 3 gate passes. Jump/Virtu conversations begin.
Day 90: Formal LP mandates with real volume justification.

Result: Clean data. Credible KPIs. Institutional LPs engaged.
```

---

## SUMMARY — THE THREE RULES

```
╔══════════════════════════════════════════════════════════════════════════╗
║                                                                        ║
║  RULE 1:  Never pair an RWA token with a volatile crypto.              ║
║           Use stablecoin intermediary ALWAYS.                          ║
║                                                                        ║
║  RULE 2:  Never deploy an AMM without an active LP mandate.            ║
║           Thin pools attract bots, not institutions.                   ║
║                                                                        ║
║  RULE 3:  Never deploy an AMM before the phase gate passes.            ║
║           The KPI dashboard must be green first.                       ║
║                                                                        ║
║  Break any of these and you're back to Phase 0.                        ║
║                                                                        ║
╚══════════════════════════════════════════════════════════════════════════╝
```

---

*CONFIDENTIAL — OPTKAS1 LLC. Internal use only.*
