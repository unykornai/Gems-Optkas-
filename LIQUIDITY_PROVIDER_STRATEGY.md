# 🟢 LIQUIDITY PROVIDER STRATEGY

**Entity:** OPTKAS1 LLC · Wyoming Series LLC · File# 2025-001184729  
**Date:** February 10, 2026  
**Version:** 1.0  
**Classification:** 🟢 INSTITUTIONAL — Execution Architecture

---

## ⚠️ CRITICAL DISTINCTION: MARKET MAKERS ≠ LENDERS

```
╔══════════════════════════════════════════════════════════════════════════════════════╗
║                                                                                    ║
║  LENDERS give you capital. They care about:                                        ║
║  → LTV, collateral, repayment, default rights                                     ║
║  → See: LENDER_PACKAGES/ (Route 2.5, Route A, Route D)                            ║
║                                                                                    ║
║  LIQUIDITY PROVIDERS give you execution. They care about:                          ║
║  → Fees, spreads, flow, inventory, settlement speed                                ║
║  → See: THIS DOCUMENT                                                              ║
║                                                                                    ║
║  DO NOT pitch an LP like a bank.                                                   ║
║  DO NOT pitch a lender like an LP.                                                 ║
║  Some firms do BOTH — but the conversations are SEPARATE.                          ║
║                                                                                    ║
╚══════════════════════════════════════════════════════════════════════════════════════╝
```

---

## TABLE OF CONTENTS

| # | Section | Purpose |
|:--|:--------|:--------|
| 1 | LP Architecture | How LPs fit the OPTKAS system |
| 2 | 3-Tier LP Roster | Tiered by urgency and capability |
| 3 | Phase Sequencing | When to contact whom |
| 4 | LP vs Lender Matrix | Which firms serve dual roles |
| 5 | Pitch Frameworks | What to say to each tier |
| 6 | Mandate Structure | Fee, inventory, duration terms |
| 7 | Execution Calendar | Day-by-day deployment |

---

## 1. LP ARCHITECTURE — HOW LIQUIDITY PROVIDERS FIT

```
╔══════════════════════════════════════════════════════════════════════════════════════╗
║                                                                                    ║
║                         OPTKAS1 CAPITAL STACK                                      ║
║                                                                                    ║
║  ┌─────────────────────────────────────────────────────────────────────────┐       ║
║  │                                                                         │       ║
║  │  LAYER 1: COLLATERAL ($5.44B total)                                    │       ║
║  │  ┌──────────┐ ┌────────────┐ ┌──────────┐ ┌──────┐ ┌──────┐          │       ║
║  │  │ TC Notes │ │ Alexandrite│ │ Rubies   │ │Rubies│ │ RE   │          │       ║
║  │  │ $5B      │ │ $42M       │ │ $376M    │ │ $12M │ │$6.6M │          │       ║
║  │  └──────────┘ └────────────┘ └──────────┘ └──────┘ └──────┘          │       ║
║  │                                                                         │       ║
║  ├─────────────────────────────────────────────────────────────────────────┤       ║
║  │                                                                         │       ║
║  │  LAYER 2: LENDING (Capital In)                                         │       ║
║  │  ┌─────────────┐ ┌────────────┐ ┌──────────────┐ ┌──────────────┐    │       ║
║  │  │ Route 1     │ │ Route 2.5  │ │ Route 5A     │ │ Route 4      │    │       ║
║  │  │ Bond ABL    │ │ Stablecoin │ │ Alex Bridge  │ │ Cross-Collat │    │       ║
║  │  │ $4M–$2B    │ │ Bridge $2M │ │ $2M–$18M     │ │ $500M–$2B    │    │       ║
║  │  └─────────────┘ └────────────┘ └──────────────┘ └──────────────┘    │       ║
║  │                                                                         │       ║
║  ├─────────────────────────────────────────────────────────────────────────┤       ║
║  │                                                                         │       ║
║  │  LAYER 3: LIQUIDITY (Execution)                    ◄── THIS DOCUMENT  │       ║
║  │  ┌─────────────┐ ┌────────────┐ ┌──────────────┐                      │       ║
║  │  │ Settlement  │ │ Market     │ │ Issuance     │                      │       ║
║  │  │ Speed       │ │ Depth      │ │ Support      │                      │       ║
║  │  │             │ │            │ │              │                      │       ║
║  │  │ Wintermute  │ │ GSR        │ │ Keyrock      │                      │       ║
║  │  │ Cumberland  │ │ Jump       │ │ B2C Group    │                      │       ║
║  │  │ FalconX     │ │ Amber      │ │ Flow Traders │                      │       ║
║  │  └─────────────┘ └────────────┘ └──────────────┘                      │       ║
║  │                                                                         │       ║
║  └─────────────────────────────────────────────────────────────────────────┘       ║
║                                                                                    ║
╚══════════════════════════════════════════════════════════════════════════════════════╝
```

### What LPs Do For OPTKAS1

| Function | Description | When Needed |
|:---------|:------------|:------------|
| **Settlement Speed** | Move $2M+ USDC/USDT same-day or next-day | Route 2.5 bridge execution |
| **Inventory** | Hold stablecoin inventory on balance sheet | Bridge backstop |
| **Market Depth** | Provide bid/ask liquidity for RWA tokens | Post-issuance (future) |
| **OTC Blocks** | Execute large stablecoin trades without slippage | Any capital movement |
| **Issuance Support** | Anchor liquidity for new token/asset issuance | GEMVLT / future instruments |

---

## 2. THREE-TIER LP ROSTER

### 🟢 TIER 1 — PRIMARY LIQUIDITY PROVIDERS (Contact First)

```
╔══════════════════════════════════════════════════════════════════════════════════════╗
║                                                                                    ║
║  These desks HOLD INVENTORY, SETTLE SAME/NEXT DAY, and understand                 ║
║  STRUCTURED LIQUIDITY. Send these first.                                           ║
║                                                                                    ║
╠══════════════════════════════════════════════════════════════════════════════════════╣
║                                                                                    ║
║  1. WINTERMUTE                                                                     ║
║     ─────────                                                                      ║
║     Strength:  Large USDC/USDT liquidity, principal risk-taking                    ║
║     Style:     Speed over process. Comfortable with bespoke structures.            ║
║     Use Case:  Route 2.5 liquidity backstop + initial RWA/stablecoin seeding       ║
║     Role:      LP first, MM later                                                  ║
║     Also:      Has Route 2.5 lending package (dual-role)                           ║
║                                                                                    ║
║  2. GSR                                                                            ║
║     ───                                                                            ║
║     Strength:  Stablecoin liquidity, structured LP programs                        ║
║     Style:     Conservative but decisive. Strong compliance posture.               ║
║     Use Case:  Anchor LP for issuance + OTC liquidity + MM mandate                 ║
║     Role:      Long-term LP relationship                                           ║
║     Also:      Has Route 2.5 lending package (dual-role)                           ║
║                                                                                    ║
║  3. CUMBERLAND (DRW)                                                               ║
║     ───────────────                                                                ║
║     Strength:  Deep USDC liquidity, institutional counterparties                   ║
║     Style:     Extremely strong balance sheet. Comfortable with escrow narratives. ║
║     Use Case:  LP for RWA rails + large OTC blocks without slippage                ║
║     Role:      Primary OTC execution partner                                       ║
║     Also:      Has Route 2.5 lending package (dual-role)                           ║
║                                                                                    ║
║  4. JUMP CRYPTO                                                                    ║
║     ───────────                                                                    ║
║     Strength:  Ultra-deep liquidity, protocol-level LP programs                    ║
║     Style:     Moves size quietly. Trusted across L1/L2 ecosystems.                ║
║     Use Case:  Future phase: protocol-backed liquidity at scale                    ║
║     Role:      Scale LP (not ideal for early bridge, better for volume)            ║
║     Note:      LP-ONLY — no lending package                                        ║
║                                                                                    ║
╚══════════════════════════════════════════════════════════════════════════════════════╝
```

### 🟡 TIER 2 — STRATEGIC / STRUCTURED LIQUIDITY PARTNERS

```
╔══════════════════════════════════════════════════════════════════════════════════════╗
║                                                                                    ║
║  Excellent once initial liquidity + custody narrative is established.               ║
║                                                                                    ║
╠══════════════════════════════════════════════════════════════════════════════════════╣
║                                                                                    ║
║  5. AMBER GROUP                                                                    ║
║     ───────────                                                                    ║
║     Strength:  Cross-venue liquidity, yield + liquidity hybrids                    ║
║     Style:     Flexible capital deployment. Comfortable with collateralized setups.║
║     Use Case:  Liquidity + credit combo. Secondary LP for RWA stablecoin.          ║
║     Also:      Has Route 2.5 lending package (dual-role)                           ║
║                                                                                    ║
║  6. FALCONX                                                                        ║
║     ────────                                                                       ║
║     Strength:  Prime brokerage, aggregated liquidity access                        ║
║     Style:     Gateway to multiple LPs. Strong institutional UX.                   ║
║     Use Case:  Routing liquidity across multiple MMs. Balance sheet + execution.   ║
║     Also:      Has Route 2.5 lending package (dual-role)                           ║
║                                                                                    ║
║  7. B2C GROUP                                                                      ║
║     ─────────                                                                      ║
║     Strength:  Stablecoin pairs, exchange liquidity programs                       ║
║     Style:     Specialized MM, not retail-focused. Works well with issuers.        ║
║     Use Case:  Stablecoin market depth on exchanges.                               ║
║     Note:      LP-ONLY — no lending package                                        ║
║                                                                                    ║
╚══════════════════════════════════════════════════════════════════════════════════════╝
```

### 🟠 TIER 3 — SPECIAL SITUATIONS / OPPORTUNISTIC

```
╔══════════════════════════════════════════════════════════════════════════════════════╗
║                                                                                    ║
║  Good for bridges, stress liquidity, or special deals. Add when volumes are real.  ║
║                                                                                    ║
╠══════════════════════════════════════════════════════════════════════════════════════╣
║                                                                                    ║
║  8. FLOW TRADERS                                                                   ║
║     ────────────                                                                   ║
║     Strength:  High-volume market making, volatility environments                  ║
║     Style:     Traditional trading DNA, risk-disciplined.                          ║
║     Use Case:  Later-stage liquidity once volumes are real.                        ║
║     Note:      LP-ONLY — no lending package                                        ║
║                                                                                    ║
║  9. VIRTU FINANCIAL                                                                ║
║     ────────────────                                                               ║
║     Strength:  Institutional liquidity, regulated venues, massive scale            ║
║     Style:     Conservative onboarding. Regulated DNA.                             ║
║     Use Case:  Long-term institutional liquidity partner.                          ║
║     Note:      LP-ONLY — no lending package                                        ║
║                                                                                    ║
║  10. KEYROCK                                                                       ║
║      ───────                                                                       ║
║      Strength:  Token issuance liquidity, European venues                          ║
║      Style:     Issuer-friendly. Structured MM mandates.                           ║
║      Use Case:  RWA/stablecoin market support post-launch.                         ║
║      Note:      LP-ONLY — no lending package                                       ║
║                                                                                    ║
╚══════════════════════════════════════════════════════════════════════════════════════╝
```

---

## 3. PHASE SEQUENCING

```
╔══════════════════════════════════════════════════════════════════════════════════════╗
║                                                                                    ║
║  PHASE 1 — EMERGENCY / BRIDGE LIQUIDITY (Now)                                     ║
║  ════════════════════════════════════════════                                       ║
║                                                                                    ║
║  CONTACT:  Wintermute, GSR, Cumberland                                             ║
║  PURPOSE:  Route 2.5 stablecoin bridge execution support                           ║
║  PITCH:    "Short-dated, collateral-secured liquidity requirement.                 ║
║             Stablecoin settlement. Control mechanics in place."                     ║
║  TIMING:   Days 0–7                                                                ║
║                                                                                    ║
║  NOTE: These 3 also have Route 2.5 LENDING packages.                              ║
║  The LP conversation is SEPARATE from the lending conversation.                    ║
║  LP = "Can you provide USDC/USDT liquidity for settlement?"                       ║
║  Lender = "Will you fund a $2M bridge against $42M collateral?"                   ║
║                                                                                    ║
╠══════════════════════════════════════════════════════════════════════════════════════╣
║                                                                                    ║
║  PHASE 2 — ISSUANCE & MARKET DEPTH (Days 7–30)                                    ║
║  ═══════════════════════════════════════════════                                    ║
║                                                                                    ║
║  ADD:      Amber Group, FalconX, Keyrock, B2C Group                                ║
║  PURPOSE:  Issuer-side liquidity program with inventory support                    ║
║  PITCH:    "Issuer-side liquidity program with inventory support.                  ║
║             RWA-backed, reserve-verified."                                          ║
║  TIMING:   Once initial bridge liquidity is secured                                ║
║                                                                                    ║
╠══════════════════════════════════════════════════════════════════════════════════════╣
║                                                                                    ║
║  PHASE 3 — INSTITUTIONAL SCALE (Days 30–90)                                        ║
║  ══════════════════════════════════════════════                                     ║
║                                                                                    ║
║  ADD:      Jump Crypto, Flow Traders, Virtu Financial                              ║
║  PURPOSE:  Regulated, transparent, reserve-verified RWA liquidity                  ║
║  PITCH:    "Regulated, transparent, reserve-verified RWA liquidity.                ║
║             Institutional-grade collateral backing."                                ║
║  TIMING:   Once volumes are real and custody narrative is proven                   ║
║                                                                                    ║
╚══════════════════════════════════════════════════════════════════════════════════════╝
```

---

## 4. LP vs LENDER MATRIX — DUAL-ROLE FIRMS

```
┌────────────────────────────┬──────────┬────────────┬──────────────────────────────┐
│  FIRM                      │ LENDER?  │ LP?        │ NOTES                        │
├────────────────────────────┼──────────┼────────────┼──────────────────────────────┤
│  Wintermute                │ ✅ R2.5  │ ✅ Tier 1  │ DUAL: LP first, lender second│
│  GSR                       │ ✅ R2.5  │ ✅ Tier 1  │ DUAL: Anchor LP + lending    │
│  Cumberland (DRW)          │ ✅ R2.5  │ ✅ Tier 1  │ DUAL: OTC + lending desk     │
│  Amber Group               │ ✅ R2.5  │ ✅ Tier 2  │ DUAL: Credit + LP hybrid     │
│  FalconX                   │ ✅ R2.5  │ ✅ Tier 2  │ DUAL: Prime broker + LP      │
├────────────────────────────┼──────────┼────────────┼──────────────────────────────┤
│  Jump Crypto               │ ❌       │ ✅ Tier 1  │ LP-ONLY: Scale phase         │
│  B2C Group                 │ ❌       │ ✅ Tier 2  │ LP-ONLY: Exchange MM         │
│  Flow Traders              │ ❌       │ ✅ Tier 3  │ LP-ONLY: Volume phase        │
│  Virtu Financial           │ ❌       │ ✅ Tier 3  │ LP-ONLY: Institutional       │
│  Keyrock                   │ ❌       │ ✅ Tier 3  │ LP-ONLY: Issuance support    │
├────────────────────────────┼──────────┼────────────┼──────────────────────────────┤
│  Galaxy Digital            │ ✅ R2.5  │ ❌         │ LENDER-ONLY (for now)        │
│  Maple Finance             │ ✅ R2.5  │ ❌         │ LENDER-ONLY                  │
│  BlockTower                │ ✅ R2.5  │ ❌         │ LENDER-ONLY                  │
│  Stone Ridge               │ ✅ R2.5  │ ❌         │ LENDER-ONLY                  │
│  Brevan Howard Digital     │ ✅ R2.5  │ ❌         │ LENDER-ONLY                  │
└────────────────────────────┴──────────┴────────────┴──────────────────────────────┘
```

### Conversation Separation Protocol

```
    ┌─────────────────────────────────────────────────────────────────────────┐
    │                                                                         │
    │  FOR DUAL-ROLE FIRMS (Wintermute, GSR, Cumberland, Amber, FalconX):    │
    │                                                                         │
    │  ✅ DO: Run two SEPARATE conversations                                 │
    │     → LP conversation: "We need stablecoin liquidity for settlement"   │
    │     → Lender conversation: "We have a $2M bridge against $42M asset"   │
    │                                                                         │
    │  ❌ DON'T: Combine into one pitch                                      │
    │     → "We need you to lend us money AND be our market maker"           │
    │     → This confuses counterparties and slows both conversations        │
    │                                                                         │
    │  ✅ DO: Lead with the LP conversation for Tier 1                       │
    │     → LP is faster to agree to (fees, not credit)                      │
    │     → Once LP relationship exists, lending intro is warmer             │
    │                                                                         │
    └─────────────────────────────────────────────────────────────────────────┘
```

---

## 5. PITCH FRAMEWORKS

### Phase 1 Pitch — Emergency / Bridge Liquidity

```
╔══════════════════════════════════════════════════════════════════════════════════════╗
║                                                                                    ║
║  TO: Wintermute / GSR / Cumberland                                                 ║
║                                                                                    ║
║  "Short-dated, collateral-secured liquidity requirement.                           ║
║   Stablecoin settlement. Control mechanics in place."                              ║
║                                                                                    ║
║  DETAILS TO INCLUDE:                                                               ║
║  → Amount: $2M USDC/USDT                                                          ║
║  → Duration: 60 days                                                               ║
║  → Collateral: $42M independently appraised physical asset in vault                ║
║  → LTV: 4.76% (21:1 overcollateralized)                                           ║
║  → Settlement: Stablecoin (USDC or USDT, lender's election)                       ║
║  → Custody: Independent vault, tripartite control                                  ║
║  → Fee: 4% flat ($80K), paid at maturity                                           ║
║                                                                                    ║
║  DO NOT SAY: "gem financing", "pawn loan", "crypto lending"                        ║
║  DO SAY: "senior secured bridge", "overcollateralized", "vault escrow"             ║
║                                                                                    ║
╚══════════════════════════════════════════════════════════════════════════════════════╝
```

### Phase 2 Pitch — Issuance & Market Depth

```
╔══════════════════════════════════════════════════════════════════════════════════════╗
║                                                                                    ║
║  TO: Amber / FalconX / Keyrock / B2C                                               ║
║                                                                                    ║
║  "Issuer-side liquidity program with inventory support."                           ║
║                                                                                    ║
║  DETAILS TO INCLUDE:                                                               ║
║  → Collateral base: $5.44B across 5 asset classes                                  ║
║  → Existing custody: STC (bonds), independent vault (gems)                         ║
║  → XRPL infrastructure: GEMVLT token deployed on mainnet                           ║
║  → Need: Market depth for RWA-backed stablecoin rails                              ║
║  → Mandate: Fee-based, inventory-supported, duration-defined                       ║
║                                                                                    ║
╚══════════════════════════════════════════════════════════════════════════════════════╝
```

### Phase 3 Pitch — Institutional Scale

```
╔══════════════════════════════════════════════════════════════════════════════════════╗
║                                                                                    ║
║  TO: Jump / Flow Traders / Virtu                                                   ║
║                                                                                    ║
║  "Regulated, transparent, reserve-verified RWA liquidity."                         ║
║                                                                                    ║
║  DETAILS TO INCLUDE:                                                               ║
║  → Proven track record from Phase 1 + Phase 2                                     ║
║  → Volume data from initial LP relationships                                       ║
║  → Regulatory compliance: Wyoming LLC, STC custody, UCC-1 filed                   ║
║  → Scale: $5B+ collateral base supports institutional volume                       ║
║                                                                                    ║
╚══════════════════════════════════════════════════════════════════════════════════════╝
```

---

## 6. MANDATE STRUCTURE — WHAT LPs WANT

```
╔══════════════════════════════════════════════════════════════════════════════════════╗
║                                                                                    ║
║  LPs want: FEES, SPREADS, FLOW                                                    ║
║  LPs do NOT want: credit risk, default exposure, long-term lockups                 ║
║                                                                                    ║
╠══════════════════════════════════════════════════════════════════════════════════════╣
║                                                                                    ║
║  STANDARD LP MANDATE TERMS:                                                        ║
║                                                                                    ║
║  ┌──────────────────────────┬────────────────────────────────────────────┐         ║
║  │  Term                    │  Standard Range                            │         ║
║  ├──────────────────────────┼────────────────────────────────────────────┤         ║
║  │  Setup Fee               │  $0 – $25,000 (waived for large mandates) │         ║
║  │  Monthly Retainer        │  $5,000 – $25,000/month                    │         ║
║  │  Performance Fee         │  % of spread captured (negotiable)         │         ║
║  │  Inventory Requirement   │  LP provides initial inventory             │         ║
║  │  Duration                │  3–12 months (renewable)                   │         ║
║  │  Exclusivity             │  Non-exclusive (multiple LPs recommended)  │         ║
║  │  Reporting               │  Weekly/monthly liquidity reports           │         ║
║  │  Minimum Spread          │  Defined per trading pair                  │         ║
║  │  Uptime                  │  95%+ market availability commitment       │         ║
║  └──────────────────────────┴────────────────────────────────────────────┘         ║
║                                                                                    ║
║  NOTE: For Route 2.5 bridge (Phase 1), the LP mandate is simpler:                 ║
║  → "Provide $2M USDC/USDT liquidity, settle in 24–48 hours, earn 4% fee."        ║
║  → No spread management needed. Just inventory + settlement speed.                 ║
║                                                                                    ║
╚══════════════════════════════════════════════════════════════════════════════════════╝
```

---

## 7. EXECUTION CALENDAR

```
╔══════════════════════════════════════════════════════════════════════════════════════╗
║                                                                                    ║
║  DAY 0 — IMMEDIATE (Phase 1 Launch)                                                ║
║  ═══════════════════════════════════                                                ║
║                                                                                    ║
║  → Contact Wintermute (LP pitch + lending pitch — SEPARATE conversations)          ║
║  → Contact GSR (LP pitch + lending pitch — SEPARATE conversations)                 ║
║  → Contact Cumberland/DRW (LP pitch + lending pitch — SEPARATE conversations)      ║
║                                                                                    ║
║  DAY 1–3 — FOLLOW-UP                                                              ║
║  ═══════════════════                                                               ║
║                                                                                    ║
║  → Send exec summaries to responsive parties                                       ║
║  → Schedule intro calls                                                            ║
║  → Parallel: Continue Route 2.5 lender outreach (Galaxy, FalconX, Amber, etc.)    ║
║                                                                                    ║
║  DAY 7–14 — PHASE 2 ACTIVATION                                                    ║
║  ═══════════════════════════════                                                   ║
║                                                                                    ║
║  → Contact Amber Group (LP pitch — already have lending package from Route 2.5)   ║
║  → Contact FalconX (LP pitch — already have lending package from Route 2.5)        ║
║  → Contact Keyrock (LP pitch — new relationship)                                   ║
║  → Contact B2C Group (LP pitch — new relationship)                                 ║
║                                                                                    ║
║  DAY 30–60 — PHASE 3 ACTIVATION                                                   ║
║  ═══════════════════════════════                                                   ║
║                                                                                    ║
║  → Contact Jump Crypto (volume data from Phase 1+2 required)                       ║
║  → Contact Flow Traders (volume data required)                                     ║
║  → Contact Virtu Financial (regulatory + volume data required)                     ║
║                                                                                    ║
╚══════════════════════════════════════════════════════════════════════════════════════╝
```

---

## RELATIONSHIP TO OTHER DOCUMENTS

| Document | Relationship |
|:---------|:-------------|
| [LENDER_PACKAGES/registry.yml](LENDER_PACKAGES/registry.yml) | LP entries marked with `type: liquidity_provider` |
| [LENDER_PACKAGES/TARGETS/](LENDER_PACKAGES/TARGETS/) | Dual-role firms have lender packages there |
| [GEM_FUNDING_PLAYBOOK.md](GEM_FUNDING_PLAYBOOK.md) | Funding routes that LPs support |
| [CROSS_COLLATERAL_STRATEGY.md](CROSS_COLLATERAL_STRATEGY.md) | Collateral stack that backs LP confidence |
| TC Repo: `07_EMERGENCY_BRIDGE_2M/` | Document pack for Route 2.5 (used by both lenders and LPs) |

---

## Version History

| Version | Date | Change |
|:--------|:-----|:-------|
| 1.0 | February 10, 2026 | Initial LP strategy. 10 firms across 3 tiers. Phase 1/2/3 sequencing. LP vs Lender matrix. Pitch frameworks. Mandate structure. |

---

*CONFIDENTIAL — OPTKAS1 LLC. Contact jimmy@optkas.com.*
