<p align="center">
  <img src="docs/assets/parametrix-logo.png" alt="Parametrix Logo" width="200"/>
</p>

<h1 align="center">Parametrix</h1>

<p align="center">
  <strong>AI-Powered Parametric Insurance for India's Gig Economy Delivery Workers</strong>
</p>

<p align="center">
  <a href="#features">Features</a> •
  <a href="#architecture">Architecture</a> •
  <a href="#ai-ml-pipeline">AI/ML Pipeline</a> •
  <a href="#adversarial-defense--anti-spoofing-strategy">Adversarial Defense</a> •
  <a href="#getting-started">Getting Started</a> •
  <a href="#api-reference">API Reference</a> •
  <a href="#contributing">Contributing</a> •
  <a href="#license">License</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/version-1.0.0-blue.svg" alt="Version"/>
  <img src="https://img.shields.io/badge/license-MIT-green.svg" alt="License"/>
  <img src="https://img.shields.io/badge/platform-India-orange.svg" alt="Platform"/>
  <img src="https://img.shields.io/badge/coverage-gig%20workers-red.svg" alt="Coverage"/>
</p>

---

## Table of Contents

1. [Overview](#overview)
2. [Problem Statement](#problem-statement)
3. [Threat Model: The 500-Agent Syndicate Attack](#threat-model-the-500-agent-syndicate-attack)
4. [Features](#features)
5. [System Architecture](#system-architecture)
6. [AI/ML Pipeline](#aiml-pipeline)
7. [Parametric Triggers](#parametric-triggers)
8. [Weekly Premium Model](#weekly-premium-model)
9. [Claims & Payout Engine](#claims--payout-engine)
10. [Adversarial Defense & Anti-Spoofing Strategy — 7-Layer Fortress](#adversarial-defense--anti-spoofing-strategy--7-layer-fortress)
11. [24-Hour Crisis Response: War Room Protocol](#24-hour-crisis-response-war-room-protocol)
12. [Protecting Honest Workers During Crisis](#protecting-honest-workers-during-crisis)
13. [Tech Stack](#tech-stack)
14. [Getting Started](#getting-started)
15. [Project Structure](#project-structure)
16. [API Reference](#api-reference)
17. [Testing](#testing)
18. [Deployment](#deployment)
19. [Contributing](#contributing)
20. [License](#license)

---

## Overview

**Parametrix** is an AI-powered parametric insurance platform purpose-built for India's gig economy delivery workers — food couriers (Zomato, Swiggy), grocery riders (Blinkit, Zepto, BigBasket), and e-commerce delivery partners (Amazon Flex, Flipkart, Delhivery). The platform provides **income protection** against external disruptions that are beyond the worker's control, such as:

- 🌧️ Extreme weather events (heavy rainfall, cyclones, heatwaves)
- 🏭 Hazardous air quality (AQI spikes above safe levels)
- 🚧 Sudden zone restrictions (curfews, Section 144, VIP movement lockdowns)
- 🌊 Flooding and waterlogging that renders delivery zones inaccessible

Unlike traditional insurance, Parametrix uses **parametric triggers** — objective, verifiable data thresholds — to automatically initiate claims and process payouts **without any manual intervention** from the worker.

> **Scope Clarification:** Parametrix is strictly an **income protection** product. It does not cover health, accident, or vehicle insurance. It compensates gig workers for lost earning potential during disruption windows.

---

## Threat Model: The 500-Agent Syndicate Attack

> ⚠️ **Real-world incident:** A sophisticated syndicate of 500 delivery workers in a Tier-1 Indian city successfully exploited a beta parametric insurance platform by organizing via Telegram groups and using advanced GPS-spoofing apps. While resting at home, they spoofed their locations into red-alert weather zones, triggering mass false payouts and draining the liquidity pool.

**Parametrix is built from the ground up to withstand this exact attack.** Simple GPS verification is officially obsolete.

| Dimension | Detail |
|---|---|
| **Attacker Profile** | Organized syndicate, ~500 delivery workers, Tier-1 city |
| **Coordination** | Localized Telegram groups (10–20 subgroups of 25–50 members) |
| **Attack Vector** | Advanced GPS-spoofing apps (FakeGPS, iSpoofer, GPS JoyStick Pro) |
| **Pattern** | Workers at home spoof GPS into active red-alert weather zones |
| **Outcome on other platforms** | Mass false payouts, liquidity pool drained |

### Attack Kill Chain

```
1. RECONNAISSANCE     → Monitor IMD alerts, identify zones that will trigger payouts
2. COORDINATION       → Telegram broadcast: target GPS coords + spoofer configs
3. POSITIONING        → 500 workers activate GPS spoofer from home
4. TRIGGER EXPLOIT    → Parametric trigger fires (legitimate weather event)
5. PAYOUT DRAIN       → 500 × ₹400 avg = ₹2,00,000 drained per event
```

### Why GPS-Only Verification is Dead

| GPS Spoofing Capability | Can Simple GPS Checks Detect? |
|---|---|
| Fake static coordinates | ❌ No |
| Simulated movement with realistic speed | ❌ No |
| Added GPS jitter (noise) | ❌ No |
| Matched altitude to terrain maps | ❌ No |
| Spoofed NMEA sentence data | ❌ No |

**Parametrix's answer: GPS is just 1 of 7 verification layers.** See [7-Layer Fortress Defense](#adversarial-defense--anti-spoofing-strategy--7-layer-fortress).

---

## Problem Statement

India's gig economy employs **15+ million delivery workers** who operate without a financial safety net. When a heavy rainstorm hits Mumbai or Delhi's AQI crosses 400, these workers face a cruel dilemma:

| Scenario | Impact |
|---|---|
| Worker stays home during extreme weather | **Zero income** for the day |
| Worker ventures out in hazardous conditions | **Health and safety risks** |
| Zone restrictions/curfews imposed | **Forced idle time**, no compensation |
| Platform reduces surge pricing post-event | **Reduced earnings** even after conditions improve |

**Current gaps:**
- Gig platforms offer **zero income protection** for weather/pollution disruptions
- Traditional insurance products require **lengthy claim processes** (7–30 days)
- Premium structures assume **monthly salary cycles**, misaligned with gig earnings
- No existing product uses **real-time parametric triggers** for gig worker coverage

---

## Features

### Core Capabilities

| Feature | Description |
|---|---|
| **Parametric Triggers** | Auto-claims via real-time weather, AQI, and restriction monitoring |
| **Weekly Premiums** | ₹49–₹149/week micro-premiums aligned with gig earning cycles |
| **Zero-Touch Claims** | No paperwork, no manual filing — triggers activate claims automatically |
| **Instant Payouts** | UPI-based payouts within 15 minutes of trigger confirmation |
| **AI Risk Scoring** | Dynamic per-worker risk assessment based on zone, history, and behavior |
| **7-Layer Fraud Defense** | Fortress-grade adversarial defense — GPS, cell tower, sensors, environment, temporal, GNN, actuarial |
| **Anti-Syndicate Engine** | Detects coordinated Telegram-organized fraud rings of 500+ workers in real-time |
| **Multi-Language UI** | Hindi, English, Tamil, Telugu, Kannada, Bengali, Marathi |
| **WhatsApp Integration** | Policy management, claim status, and payouts via WhatsApp chatbot |

### For Gig Workers
- 📱 Simple onboarding via mobile number + Aadhaar e-KYC
- 💰 Weekly premium deduction from gig platform earnings (opt-in)
- 🔔 Real-time notifications when a trigger is approaching their zone
- 💸 Instant UPI payout when a parametric event is confirmed
- 📊 Dashboard showing protection history and claim records

### For Platform Partners (Zomato, Swiggy, etc.)
- 🤝 API integration for worker enrollment and premium collection
- 📈 Analytics dashboard on workforce protection coverage
- 🏷️ Co-branded insurance offering to improve rider retention
- 📋 Compliance reporting for gig worker welfare mandates

---

## System Architecture

```
┌─────────────────────────────────────────────────────────────────────────┐
│                         PARAMETRIX PLATFORM                             │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌────────────┐  │
│  │  Mobile App   │  │  WhatsApp    │  │ Partner API  │  │  Admin     │  │
│  │  (React       │  │  Chatbot     │  │ (REST/gRPC)  │  │  Dashboard │  │
│  │   Native)     │  │  (Twilio)    │  │              │  │  (React)   │  │
│  └──────┬────────┘  └──────┬───────┘  └──────┬───────┘  └──────┬─────┘  │
│         │                  │                 │                 │        │
│  ───────┴──────────────────┴─────────────────┴─────────────────┴─────── │
│                          API Gateway (Kong)                              │
│  ────────────────────────────────────────────────────────────────────── │
│         │                  │                 │                 │        │
│  ┌──────┴────────┐  ┌──────┴───────┐  ┌──────┴───────┐  ┌─────┴──────┐ │
│  │  Auth &       │  │  Policy      │  │  Claims      │  │  Payout    │ │
│  │  Identity     │  │  Engine      │  │  Engine      │  │  Engine    │ │
│  │  Service      │  │              │  │  + Circuit   │  │  (UPI)     │ │
│  │              │  │              │  │  Breaker     │  │            │ │
│  └──────────────┘  └──────────────┘  └──────────────┘  └────────────┘ │
│         │                  │                 │                 │        │
│  ───────┴──────────────────┴─────────────────┴─────────────────┴─────── │
│                       Event Bus (Apache Kafka)                           │
│  ────────────────────────────────────────────────────────────────────── │
│         │           │            │            │            │            │
│  ┌──────┴──────┐ ┌──┴─────┐ ┌───┴──────┐ ┌───┴────────┐ ┌┴──────────┐ │
│  │  Trigger    │ │ AI/ML  │ │  7-LAYER │ │  Ring      │ │  Notif.   │ │
│  │  Monitor    │ │Pricing │ │  FRAUD   │ │  Detection │ │  Service  │ │
│  │  Service    │ │Engine  │ │  FORTRESS│ │  (GNN)     │ │           │ │
│  └──────┬──────┘ └────────┘ └────┬─────┘ └────────────┘ └───────────┘ │
│         │                        │                                      │
│         │          ┌─────────────┴──────────────────┐                   │
│         │          │     7-LAYER VERIFICATION        │                   │
│         │          │  L1: GPS Signal Metadata        │                   │
│         │          │  L2: Environmental Correlation   │                   │
│         │          │  L3: Device Integrity & Sensors  │                   │
│         │          │  L4: Cell Tower Triangulation    │                   │
│         │          │  L5: Temporal Behavior Analysis  │                   │
│         │          │  L6: GNN Fraud Ring Detection    │                   │
│         │          │  L7: Actuarial Anomaly Detection │                   │
│         │          └────────────────────────────────┘                   │
│         │                                                               │
│  ┌──────┴───────┐  ┌──────────────┐  ┌──────────────┐  ┌────────────┐  │
│  │  Weather     │  │  AQI         │  │  Govt.       │  │  Telecom   │  │
│  │  Data API    │  │  Data API    │  │  Alert API   │  │  Tower API │  │
│  │  (IMD/OWM)   │  │  (CPCB)      │  │  (NDMA)      │  │  (CellDB)  │  │
│  └──────────────┘  └──────────────┘  └──────────────┘  └────────────┘  │
│                                                                         │
│  ┌─────────────────────────────────────────────────────────────────┐    │
│  │                      Data Layer                                 │    │
│  │  PostgreSQL │ Redis │ TimescaleDB │ S3 │ Neo4j (Fraud Graph)   │    │
│  └─────────────────────────────────────────────────────────────────┘    │
└─────────────────────────────────────────────────────────────────────────┘
```

### Microservices Breakdown

| Service | Responsibility | Port |
|---|---|---|
| `auth-service` | Aadhaar e-KYC, phone OTP, JWT tokens | 3001 |
| `policy-engine` | Plan selection, premium calculation, policy lifecycle | 3002 |
| `trigger-monitor` | Real-time weather/AQI/restriction data ingestion | 3003 |
| `claims-engine` | Trigger validation, claim creation, eligibility check, **actuarial circuit breaker** | 3004 |
| `payout-engine` | UPI integration, instant settlement, reconciliation | 3005 |
| `ai-pricing` | Dynamic premium pricing, risk scoring | 3006 |
| `fraud-fortress` | **7-layer verification pipeline** — GPS, environment, device, cell tower, temporal, GNN, actuarial | 3007 |
| `ring-detector` | **GNN-based fraud ring detection**, community detection, Telegram pattern analysis | 3010 |
| `notification-service` | Push, SMS, WhatsApp alerts | 3008 |
| `admin-dashboard` | Internal ops, analytics, manual override, war-room console | 3009 |

---

## AI/ML Pipeline

### 1. Dynamic Risk Assessment

Each worker receives a personalized **Risk Score (0–100)** computed weekly:

```
Risk Score = f(Zone Risk, Seasonal Factor, Historical Claims, Behavioral Score)
```

**Model:** Gradient Boosted Trees (XGBoost) trained on:

| Feature Category | Features |
|---|---|
| **Geospatial** | Worker's primary zone, flood-prone areas, AQI hotspots |
| **Temporal** | Monsoon season, winter smog period, festival rush |
| **Historical** | Past claim frequency, claim amounts, trigger proximity |
| **Behavioral** | Average active hours, zone coverage pattern, app engagement |
| **Platform** | Order volume trends, surge pricing history, cancellation rates |

### 2. Predictive Premium Pricing

```python
# Simplified pricing model
class PremiumPricer:
    def calculate_weekly_premium(self, worker_profile):
        base_rate = self.get_base_rate(worker_profile.zone)           # ₹30-80
        risk_multiplier = self.risk_model.predict(worker_profile)      # 0.6-2.5x
        seasonal_adj = self.seasonal_model.get_factor(current_week)    # 0.8-1.8x
        loyalty_discount = self.get_loyalty_discount(worker_profile)   # 0.85-1.0x
        
        premium = base_rate * risk_multiplier * seasonal_adj * loyalty_discount
        return clamp(premium, min=49, max=149)  # Weekly bounds in ₹
```

**Key pricing principles:**
- **No flat pricing** — every worker gets a personalized premium
- **Seasonal adjustment** — premiums rise slightly before monsoon (priced-in risk)
- **Loyalty rewards** — long-tenure workers with clean records get discounts
- **Zone-specific base rates** — Mumbai coastal zones vs. Bangalore tech park zones

### 3. Trigger Prediction

An LSTM-based time-series model predicts upcoming parametric events 6–24 hours in advance:

```
Input:  [weather_history, satellite_imagery, AQI_trends, govt_alert_signals]
Output: P(trigger_event | zone, time_window)
```

This powers:
- **Pre-alerts** to workers ("Heavy rain expected in your zone in 4 hours")
- **Reserve provisioning** for the payout engine
- **Surge premium windows** (optional advance coverage purchase)

### 4. Fraud Detection (Detail in Adversarial Defense Section)

A multi-model ensemble combining:
- **Isolation Forest** for anomaly detection
- **Graph Neural Network** for fraud ring identification
- **Siamese Network** for GPS trajectory verification
- **Rule-based filters** for known fraud patterns

---

## Parametric Triggers

### Trigger Definitions

| Trigger | Data Source | Threshold | Payout |
|---|---|---|---|
| **Heavy Rainfall** | IMD + OpenWeatherMap | > 64.5 mm/hr (very heavy) | ₹300–500/day |
| **Extreme Heat** | IMD | > 45°C for > 3 hours | ₹200–350/day |
| **Hazardous AQI** | CPCB CAAQMS | AQI > 400 (severe+) | ₹250–400/day |
| **Cyclone Warning** | IMD Cyclone Division | Orange/Red alert | ₹500–800/day |
| **Flooding** | CWC + IMD | Area flood alert + waterlog reports | ₹400–600/day |
| **Zone Restriction** | Govt. gazette + news API | Section 144 / curfew | ₹350–500/day |
| **Visibility** | IMD | < 50m fog for > 4 hours | ₹200–300/day |

### Trigger Verification Pipeline

```
Data Source (IMD/CPCB/CWC)
    │
    ▼
┌─────────────────────┐
│  Multi-Source        │    Cross-reference ≥2 independent sources
│  Correlation Engine  │    before confirming a trigger
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│  Geospatial Mapping │    Map trigger to affected pin codes
│  (H3 Hexagonal Grid)│    and delivery zones
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│  Worker Overlap      │    Identify enrolled workers whose
│  Detection           │    active zone intersects trigger zone
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│  Claim Auto-         │    Create claim records for eligible
│  Generation          │    workers — ZERO manual input required
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│  Fraud Screening     │    Run claim through adversarial
│  (< 2 seconds)       │    defense pipeline
└─────────┬───────────┘
          │
          ▼
┌─────────────────────┐
│  Payout Execution    │    UPI instant transfer to worker's
│  (< 15 minutes)      │    linked bank account
└─────────────────────┘
```

---

## Weekly Premium Model

### Why Weekly?

| Aspect | Monthly Premium (Traditional) | Weekly Premium (Parametrix) |
|---|---|---|
| **Payment frequency** | Once/month | Every Monday |
| **Alignment with income** | ❌ Gig workers earn daily/weekly | ✅ Matches weekly payout cycles |
| **Affordability perception** | ₹199–599/month feels large | ₹49–149/week feels manageable |
| **Flexibility** | Locked for 30 days | Skip any week (pause coverage) |
| **Churn risk** | High — big upfront commitment | Low — low commitment barrier |

### Premium Tiers

| Tier | Weekly Cost | Coverage | Max Payout/Week |
|---|---|---|---|
| **🟢 Shield** | ₹49/week | Weather only (rain, heat) | ₹500 |
| **🔵 Guard** | ₹89/week | Weather + AQI | ₹1,000 |
| **🟣 Fortress** | ₹149/week | Weather + AQI + Zone Restrictions | ₹2,000 |

### Premium Collection Methods
- **Auto-deduct** from gig platform earnings (Zomato/Swiggy partner API)
- **UPI Autopay** (weekly mandate via NPCI)
- **Wallet deduction** (Paytm, PhonePe, Amazon Pay)

---

## Claims & Payout Engine

### Claim Lifecycle

```
TRIGGER_DETECTED → CLAIM_CREATED → FRAUD_SCREENING → APPROVED/FLAGGED → PAYOUT_INITIATED → SETTLED
     (0s)            (< 1s)          (< 2s)           (< 5s)            (< 30s)          (< 15m)
```

### Payout Channels

| Channel | Speed | Availability |
|---|---|---|
| **UPI Instant** | < 15 minutes | 24/7 |
| **IMPS** | < 30 minutes | 24/7 |
| **Bank Transfer (NEFT)** | < 2 hours | Business hours |
| **Wallet Credit** | < 5 minutes | 24/7 |

### Payout Calculation

```python
def calculate_payout(trigger, worker, policy):
    base_payout = TRIGGER_PAYOUT_MAP[trigger.type][trigger.severity]
    
    # Pro-rate based on overlap between trigger window and worker's active hours
    active_overlap = compute_overlap(trigger.window, worker.typical_active_hours)
    overlap_factor = active_overlap / trigger.window.duration
    
    # Zone impact factor (worker closer to epicenter gets higher payout)
    zone_impact = compute_zone_impact(worker.primary_zone, trigger.affected_zones)
    
    payout = base_payout * overlap_factor * zone_impact
    return min(payout, policy.max_weekly_payout - policy.week_claims_total)
```

---

## Adversarial Defense & Anti-Spoofing Strategy — 7-Layer Fortress

> **Simple GPS verification is a single lock on the front door. Parametrix is a vault with 7 independent locking mechanisms.** An attacker must defeat ALL 7 simultaneously — which is computationally and practically infeasible.

```
┌──────────────────────────────────────────────────────────────────────┐
│                                                                      │
│    LAYER 7  ║  📊 ACTUARIAL ANOMALY DETECTION                       │
│    ─────────╬────────────────────────────────────────────────────     │
│             ║  Statistical deviation from zone baselines             │
│                                                                      │
│    LAYER 6  ║  🕸️ GRAPH NEURAL NETWORK (RING DETECTION)             │
│    ─────────╬────────────────────────────────────────────────────     │
│             ║  Community detection across worker relationships       │
│                                                                      │
│    LAYER 5  ║  ⏱️ TEMPORAL BEHAVIOR ANALYSIS                        │
│    ─────────╬────────────────────────────────────────────────────     │
│             ║  Claim timing correlation, pre-event behavior gaps     │
│                                                                      │
│    LAYER 4  ║  📡 CELL TOWER & NETWORK TRIANGULATION                │
│    ─────────╬────────────────────────────────────────────────────     │
│             ║  Physical radio signal vs claimed GPS position         │
│                                                                      │
│    LAYER 3  ║  📱 DEVICE INTEGRITY & SENSOR FUSION                  │
│    ─────────╬────────────────────────────────────────────────────     │
│             ║  Accelerometer, gyroscope, barometer, mock detection   │
│                                                                      │
│    LAYER 2  ║  🌦️ ENVIRONMENTAL CORRELATION                        │
│    ─────────╬────────────────────────────────────────────────────     │
│             ║  Does the device sense weather matching the trigger?   │
│                                                                      │
│    LAYER 1  ║  📍 GPS SIGNAL ANALYSIS (ENHANCED)                    │
│    ─────────╬────────────────────────────────────────────────────     │
│             ║  Satellite count, HDOP, C/N₀, fix type analysis       │
│                                                                      │
└──────────────────────────────────────────────────────────────────────┘
```

### LAYER 1: Enhanced GPS Signal Analysis

Goes beyond coordinates — analyzes **raw satellite signal metadata** that spoofing apps cannot replicate.

| Signal Property | Genuine GPS | Spoofed GPS | Detection |
|---|---|---|---|
| **Satellite Count** | 6–12, varies naturally | Fixed at 1 or max value | ✅ Flag if static |
| **C/N₀ (Carrier-to-Noise)** | Varies per satellite (25–50 dB-Hz) | Identical across channels | ✅ Flag if variance < threshold |
| **HDOP/VDOP** | Fluctuates (0.8–3.0) | Perfect (1.0) or static | ✅ Flag if suspiciously stable |
| **Fix Type** | Transitions 2D/3D | Always 3D | ✅ Flag if no transitions |
| **Time-to-First-Fix** | 2–30s (cold/warm) | Instant (< 100ms) | ✅ Flag if near-zero |
| **Multi-constellation** | GPS + GLONASS + Galileo + NavIC | GPS-only | ✅ Flag if single constellation |

```python
class EnhancedGPSAnalyzer:
    def analyze_signal_authenticity(self, raw_gps_data):
        score = 1.0
        # Satellite count variance (too stable = spoofed)
        if np.var(raw_gps_data.satellite_counts[-30:]) < 0.5: score -= 0.25
        # C/N₀ should vary across satellites (identical = fake)
        if np.var(raw_gps_data.carrier_to_noise_per_satellite) < 2.0: score -= 0.30
        # HDOP should fluctuate naturally
        if np.count_nonzero(np.diff(raw_gps_data.hdop_history[-60:])) < 5: score -= 0.20
        # India should see GPS + NavIC minimum
        if len(set(raw_gps_data.satellite_systems)) < 2: score -= 0.15
        # Direct mock location flag (Android API)
        if raw_gps_data.is_from_mock_provider: score -= 0.50
        return max(score, 0.0)
```

### LAYER 2: Environmental Correlation

**Core Idea:** If a worker claims to be in torrential rain, their phone's ambient sensors should confirm it. A spoofer at home in a dry area **will fail this check**.

| Sensor | During Heavy Rain | At Home (Dry) | Detectable? |
|---|---|---|---|
| **Barometric Pressure** | Rapid drop (low pressure) | Stable indoor pressure | ✅ Yes |
| **Ambient Light** | Low (dark clouds) | Normal indoor lighting | ✅ Yes |
| **Microphone (ambient)** | Rain noise signature | Home sounds (TV, silence) | ✅ Yes |
| **Temperature** | Drop during rain | Stable indoor temp | ✅ Yes |

**Even the most advanced GPS spoofer cannot fake their phone's barometer, light sensor, and microphone simultaneously.**

### LAYER 3: Device Integrity & Sensor Fusion

Detects whether the device has been tampered with to enable spoofing:

- **Mock Location Provider Detection** (Android API)
- **Developer Options / Root / Jailbreak Detection**
- **Known Spoofing App Detection** (FakeGPS, iSpoofer, GPS JoyStick)
- **Accelerometer-GPS Mismatch** — the critical check:

```
GENUINE WORKER ON BIKE IN RAIN:
  GPS:            Moving at 15-25 km/h with natural variations
  Accelerometer:  Vibration patterns consistent with bike + road
  Gyroscope:      Lean angles consistent with turns

SPOOFER AT HOME ON COUCH:
  GPS (spoofed):  "Moving at 20 km/h" through rain zone
  Accelerometer:  FLAT LINE — no vibration, no movement  ← CAUGHT
  Gyroscope:      FLAT LINE — no turns, no lean           ← CAUGHT
```

### LAYER 4: Cell Tower & Network Triangulation ⚡ THE KILLSHOT

**The spoofer's Achilles heel.** GPS can be spoofed in software, but your phone's **radio connection to cell towers is a hardware-level physical reality** that cannot be faked from an app.

```python
class CellTowerVerifier:
    def verify_location_via_network(self, device_data, claimed_gps):
        # Triangulate ACTUAL position from connected cell towers
        connected_towers = device_data.cell_tower_info  # MCC, MNC, LAC, CID
        tower_locations = self.tower_db.get_locations(connected_towers)
        triangulated_position = self.triangulate(towers=tower_locations,
                                                  signal_strengths=device_data.signal_strengths)
        
        distance_km = haversine(triangulated_position, claimed_gps)
        if distance_km > 2.0:  # >2km discrepancy = GPS spoofing confirmed
            return VerificationResult(status='GPS_CELL_MISMATCH', confidence=0.95,
                                      discrepancy_km=distance_km)
```

```
SPOOFER'S SITUATION:
  Physical Location:  Home in Andheri West, Mumbai
  Connected Towers:   Andheri West towers
  Spoofed GPS:        Dahisar (flood zone), 22 km away
  
  RESULT: Cell tower says Andheri, GPS says Dahisar
  >>> DISCREPANCY: 22 KM — INSTANT RED FLAG <<<
```

**To defeat cell tower verification, an attacker would need to physically relocate to the target zone — which defeats the entire purpose of the fraud.**

### LAYER 5: Temporal Behavior Analysis

Detects the **coordinated timing** signature of a Telegram-organized syndicate.

| Signal | Genuine Worker | Syndicate Member |
|---|---|---|
| **Zone entry time** | Was in zone hours before event | "Appears" within minutes of trigger |
| **Claim timing** | Naturally distributed over 10–60 min | Clustered within 2–5 min (Telegram broadcast lag) |
| **Pre-event activity** | Active orders, movement, deliveries | No order history in zone before event |
| **Post-event behavior** | Resumes deliveries after event | Immediately "leaves" zone post-payout |

```python
class TemporalAnalyzer:
    def detect_pre_event_anomaly(self, worker, trigger):
        # Check: was worker in the zone BEFORE the trigger was announced?
        pre_history = self.get_location_history(worker,
            time_range=(trigger.announce_time - timedelta(hours=3), trigger.announce_time))
        
        was_already_in_zone = any(self.is_in_zone(loc, trigger.zone) for loc in pre_history)
        if not was_already_in_zone:
            appearance = self.first_appearance_in_zone(worker, trigger.zone)
            if appearance > trigger.announce_time:
                # Appeared AFTER announcement — classic spoofer pattern
                return SuspicionResult(flag='POST_ANNOUNCEMENT_ENTRY', confidence=0.88)
```

### LAYER 6: Graph Neural Network — Fraud Ring Detection

Looks at **relationships between workers** to uncover the hidden syndicate structure.

**7 Edge Types in the Suspicion Graph:**

| Edge Type | What It Reveals |
|---|---|
| **Shared Device Fingerprint** | Device farms or phone sharing |
| **Same IP Subnet** | Ring members on same WiFi/VPN |
| **Telegram Broadcast Timing** | Claims follow message propagation delay (30s–3min) |
| **Payout Account Links** | Multiple workers funneling to same bank account |
| **Referral Chain** | Same recruiter referred 150+ members |
| **GPS Trajectory Similarity** | Identical spoofed route templates (cosine > 0.93) |
| **Spoofing App Overlap** | Same spoofing tools installed |

```
DETECTING THE 500-WORKER SYNDICATE:

  GRAPH CONSTRUCTION:
    ├─ 127 shared IP subnets detected
    ├─ 43 shared device fingerprints (device farm)
    ├─ 312 claim timestamps match Telegram broadcast pattern
    ├─ 67 payout accounts receiving from multiple workers
    ├─ 489 workers trace to 3 referral sources
    └─ 500 GPS trajectories cluster into just 12 templates

  COMMUNITY DETECTION (Louvain + GNN):
    ╔══════════════════════════════════════════════════╗
    ║  FRAUD RING DETECTED                             ║
    ║  Members: 487 / 500 claims flagged               ║
    ║  Confidence: 0.97                                ║
    ║  Sub-communities: 18 Telegram groups identified  ║
    ║  Ring Leaders: 3 referral source accounts         ║
    ╚══════════════════════════════════════════════════╝

  Remaining 13 claims → genuine workers → AUTO-APPROVED
```

### LAYER 7: Actuarial Anomaly Detection

The ultimate statistical sanity check — does the claim volume make mathematical sense?

```python
class ActuarialAnomalyDetector:
    def check_zone_claim_rate(self, zone, trigger_event, claims):
        expected = self.get_historical_worker_density(zone=zone,
            day_of_week=trigger_event.day, hour=trigger_event.hour)
        actual = len(claims)
        p_value = poisson.sf(actual - 1, mu=expected * 0.7)
        
        if p_value < 0.001:  # <0.1% probability
            return AnomalyResult(flag='IMPLAUSIBLE_CLAIM_VOLUME',
                expected=expected, actual=actual,
                detail=f'Zone has {expected} workers, got {actual} claims (p={p_value:.6f})')
```

```
SYNDICATE ATTACK EXAMPLE:
  Zone: Dahisar, Mumbai | Expected claims: ~30 | Actual claims: 530
  Deviation: 17.6σ | P-value: < 10⁻⁶⁸
  
  VERDICT: ████ ACTUARIAL CIRCUIT BREAKER ACTIVATED ████
```

### Syndicate Defense Summary

| Attack Capability | Other Platforms | Parametrix |
|---|---|---|
| GPS coordinate spoofing | ❌ Defeated | ✅ Layer 1 catches signal metadata |
| Realistic fake trajectories | ❌ Defeated | ✅ Layer 3 (accelerometer mismatch) |
| 500 simultaneous claims | ❌ Pool drained | ✅ Layer 7 triggers circuit breaker |
| Coordinated Telegram timing | ❌ Undetected | ✅ Layer 5 detects broadcast pattern |
| Home WiFi while spoofing | ❌ Undetected | ✅ Layer 4 exposes real cell tower location |
| Claiming rain from dry home | ❌ Undetected | ✅ Layer 2 confirms dry conditions |
| Organized ring structure | ❌ Undetected | ✅ Layer 6 maps the entire ring |

---

## 24-Hour Crisis Response: War Room Protocol

When the syndicate attacks, this is Parametrix's automated minute-by-minute response:

### Phase 1: Detection (T+0 to T+2 minutes)

```
T+0:00  │ Severe weather trigger fires for Zone X
T+0:05  │ Claims engine begins auto-generating claims
T+0:15  │ LAYER 7 fires: claim volume is 17σ above baseline
        │ ┌────────────────────────────────────────────┐
        │ │ 🚨 ACTUARIAL CIRCUIT BREAKER ACTIVATED      │
        │ │ Zone X claims PAUSED for enhanced screening │
        │ └────────────────────────────────────────────┘
T+0:20  │ LAYER 4: Cell tower verification on batch
        │ → 487/530 claims show GPS-cell tower mismatch (>5 km)
T+0:45  │ LAYER 3: Device integrity scan returns
        │ → 312 devices have mock location enabled
        │ → 156 devices have known GPS spoofing apps
T+1:00  │ LAYER 5: Temporal analysis complete
        │ → 489 claims cluster within 3-minute window
        │ → Telegram broadcast timing pattern detected
T+1:30  │ LAYER 6: GNN fraud ring detection complete
        │ → 18 sub-communities identified, 3 ring leaders flagged
T+2:00  │ LAYER 2: Environmental data rules out 487 claims
        │ → No barometric pressure drop on these devices
        │ → Indoor lighting confirmed on 400+ devices
```

### Phase 2: Surgical Response (T+2 to T+10 minutes)

```
T+2:00  │ GENUINE CLAIMS (43 workers) — IMMEDIATELY APPROVED
        │ → Cell towers confirm physical presence in Zone X
        │ → Accelerometer shows outdoor movement
        │ → Barometer correlates with storm system
        │ → Payout initiated via UPI (< 15 minutes)
        │
T+3:00  │ FRAUDULENT CLAIMS (487 workers) — BATCH SUSPENDED
        │ → Evidence packages generated per worker
        │ → Ring structure documented with graph visualization
        │ → Zero payouts to syndicate members
        │
T+5:00  │ RING LEADER ACCOUNTS — ESCALATED
        │ → 3 referral source accounts identified
        │ → Each leader referred 150-200 members
        │
T+10:00 │ LIQUIDITY POOL STATUS: ✅ PROTECTED
        │ → ₹0 fraudulent payouts | ₹17,200 genuine payouts processed
```

### Phase 3: Hardening (T+10 min to T+24 hours)

```
T+1 hr  │ Human fraud team reviews all 487 flagged accounts
T+4 hr  │ Syndicate accounts permanently restricted
        │ → Device fingerprints + UPI accounts blacklisted
T+8 hr  │ ML models retrained with new attack patterns
T+12 hr │ Partner platforms (Zomato, Swiggy) notified via secure API
T+24 hr │ Post-incident report: 100% fraud caught, 0% false positives
```

---

## Protecting Honest Workers During Crisis

### Why the 43 Genuine Workers Were NOT Delayed

```
GENUINE WORKER CHECK (per worker, < 2 seconds):

  ✅ Layer 1: GPS shows continuous presence in Zone X since morning
  ✅ Layer 2: Barometer confirms storm pressure drop (-8 hPa)
  ✅ Layer 3: Accelerometer shows bike riding → stationary (sheltering)
  ✅ Layer 4: Cell tower confirms Zone X physical presence
  ✅ Layer 5: Was delivering orders 2 hours BEFORE trigger
  ✅ Layer 6: No connections to syndicate graph (isolated node)
  ✅ Layer 7: Claim within normal zone volume

  RESULT: AUTO-APPROVE → Payout in 12 minutes via UPI
```

### Handling Workers with Weak Data (Network Drop / Old Phone)

```
  ✅ Layer 1: GPS has 20-min gap (phone restart in rain)
  ⚠️ Layer 2: No barometer (old phone, no sensor)
  ✅ Layer 3: Accelerometer showed outdoor exposure before gap
  ✅ Layer 4: Cell tower confirms Zone X (even without GPS)
  ✅ Layer 5: 6 deliveries in zone today
  ✅ Layer 6: No syndicate connections
  ✅ Layer 7: Expected claim rate

  RESULT: SOFT FLAG (Tier 2)
  → Payout issued within 30 minutes
  → Network Exception Handler confirms tower outages in Zone X
  → Flag automatically cleared, trust score unaffected
```

### Three-Tier Claim Resolution

| Tier | % of Claims | Authenticity Score | Action |
|---|---|---|---|
| **Tier 1: Auto-Approve** | 85% | ≥ 0.7 | Instant UPI payout (< 15 min), zero friction |
| **Tier 2: Soft Flag** | 12% | 0.4 – 0.7 | **Pay first, investigate later** — payout in 30 min |
| **Tier 3: Hard Flag** | 3% | < 0.4 | Held for manual review (max 4 hrs), clear notification sent |

### Trust Score & Cooling Mechanism

| Level | Score | Benefits |
|---|---|---|
| 🟢 **Trusted** | 80–100 | All claims auto-approved |
| 🔵 **Standard** | 50–79 | Normal processing |
| 🟡 **Under Review** | 30–49 | Soft flags more frequent, payouts still issued |
| 🔴 **Restricted** | 0–29 | Manual review (only after confirmed fraud) |

**Cooling mechanism:** A single suspicious event does NOT reduce trust. Requires **3+ corroborated events** in 30 days. Weather-related network gaps are **automatically excluded** from trust calculations.

### Appeal & Grievance System

```
L1: Auto-review (relaxed thresholds, ISP outage data) → Approved? → Payout + ₹25 credit
L2: Human reviewer (4-hour SLA, worker submits evidence) → Approved? → Payout + ₹50 credit
L3: Independent Ombudsman (48-hour review, final binding decision)
```

### Network Exception Handler

```python
class NetworkExceptionHandler:
    def evaluate_network_drop(self, worker, claim, trigger):
        tower_status = self.telecom_api.get_tower_status(zone=worker.zone,
                                                          time_window=trigger.window)
        isp_status = self.isp_api.get_outage_reports(worker.zone)
        
        if tower_status.has_outage or isp_status.has_outage:
            claim.network_exception = True
            claim.data_gap_excused = True
            return ClaimDecision.AUTO_APPROVE  # Do NOT flag this worker
        
        if trigger.severity >= Severity.SEVERE:
            self.apply_relaxed_thresholds(claim)  # Lenient during severe weather
```

---

## Tech Stack

### Backend
| Component | Technology |
|---|---|
| **API Services** | Node.js (Express) / Python (FastAPI) |
| **Event Streaming** | Apache Kafka |
| **Task Queue** | Celery + Redis |
| **API Gateway** | Kong |

### AI/ML
| Component | Technology |
|---|---|
| **Risk Models** | XGBoost, LightGBM |
| **Time Series** | LSTM (PyTorch) |
| **Fraud Detection** | Isolation Forest, GNN (PyTorch Geometric) |
| **GPS Verification** | Siamese Networks (TensorFlow) |
| **Feature Store** | Feast |
| **Model Serving** | TensorFlow Serving / TorchServe |
| **Experiment Tracking** | MLflow |

### Data
| Component | Technology |
|---|---|
| **Primary DB** | PostgreSQL 15 |
| **Time Series DB** | TimescaleDB |
| **Cache** | Redis Cluster |
| **Object Storage** | AWS S3 / MinIO |
| **Geospatial** | PostGIS + H3 (Uber hexagonal grid) |

### Frontend
| Component | Technology |
|---|---|
| **Mobile App** | React Native |
| **Admin Dashboard** | React + Vite |
| **WhatsApp Bot** | Twilio API |

### Infrastructure
| Component | Technology |
|---|---|
| **Cloud** | AWS (ap-south-1 Mumbai) |
| **Containers** | Docker + Kubernetes (EKS) |
| **CI/CD** | GitHub Actions |
| **Monitoring** | Prometheus + Grafana |
| **Logging** | ELK Stack |

---

## Getting Started

### Prerequisites

- **Node.js** >= 18.x
- **Python** >= 3.10
- **Docker** & **Docker Compose**
- **PostgreSQL** 15+
- **Redis** 7+
- **Kafka** 3.x (or use Docker Compose)

### Quick Start

```bash
# 1. Clone the repository
git clone https://github.com/your-org/parametrix.git
cd parametrix

# 2. Copy environment variables
cp .env.example .env
# Edit .env with your API keys (IMD, CPCB, UPI gateway, etc.)

# 3. Start infrastructure services
docker-compose up -d postgres redis kafka

# 4. Run database migrations
npm run db:migrate

# 5. Seed initial data (zones, trigger thresholds, sample plans)
npm run db:seed

# 6. Start all microservices in development mode
npm run dev

# 7. Start the ML model server
cd ml-service
pip install -r requirements.txt
python serve.py

# 8. Access the admin dashboard
open http://localhost:3009
```

### Environment Variables

```env
# Database
DATABASE_URL=postgresql://parametrix:password@localhost:5432/parametrix

# Redis
REDIS_URL=redis://localhost:6379

# Kafka
KAFKA_BROKERS=localhost:9092

# Weather API (Indian Meteorological Department)
IMD_API_KEY=your_imd_api_key
OPENWEATHERMAP_API_KEY=your_owm_api_key

# Air Quality (Central Pollution Control Board)
CPCB_API_KEY=your_cpcb_api_key

# UPI Payment Gateway
UPI_GATEWAY_URL=https://api.payment-provider.com
UPI_MERCHANT_ID=your_merchant_id
UPI_SECRET_KEY=your_secret_key

# Aadhaar e-KYC
AADHAAR_API_KEY=your_aadhaar_api_key

# Twilio (WhatsApp)
TWILIO_ACCOUNT_SID=your_twilio_sid
TWILIO_AUTH_TOKEN=your_twilio_token

# ML Model Server
ML_MODEL_SERVER_URL=http://localhost:8501
```

---

## Project Structure

```
parametrix/
├── services/
│   ├── auth-service/            # Authentication & KYC
│   │   ├── src/
│   │   ├── tests/
│   │   └── Dockerfile
│   ├── policy-engine/           # Policy management
│   │   ├── src/
│   │   ├── tests/
│   │   └── Dockerfile
│   ├── trigger-monitor/         # Real-time trigger monitoring
│   │   ├── src/
│   │   │   ├── sources/         # IMD, CPCB, CWC integrations
│   │   │   ├── correlation/     # Multi-source verification
│   │   │   └── mapping/         # H3 geospatial mapping
│   │   ├── tests/
│   │   └── Dockerfile
│   ├── claims-engine/           # Claim generation & processing
│   │   ├── src/
│   │   ├── tests/
│   │   └── Dockerfile
│   ├── payout-engine/           # UPI/IMPS payout processing
│   │   ├── src/
│   │   ├── tests/
│   │   └── Dockerfile
│   ├── ai-pricing/              # ML-based pricing engine
│   │   ├── models/
│   │   ├── training/
│   │   ├── serving/
│   │   └── Dockerfile
│   ├── fraud-engine/            # Adversarial defense & anti-spoofing
│   │   ├── models/
│   │   │   ├── isolation_forest/
│   │   │   ├── gnn_ring_detector/
│   │   │   ├── siamese_gps/
│   │   │   └── network_exception/
│   │   ├── src/
│   │   │   ├── gps_verification.py
│   │   │   ├── ring_detector.py
│   │   │   ├── anomaly_scorer.py
│   │   │   └── appeal_handler.py
│   │   ├── tests/
│   │   └── Dockerfile
│   └── notification-service/    # Push, SMS, WhatsApp alerts
│       ├── src/
│       ├── templates/
│       ├── tests/
│       └── Dockerfile
├── mobile-app/                  # React Native app
│   ├── src/
│   ├── android/
│   ├── ios/
│   └── package.json
├── admin-dashboard/             # React admin panel
│   ├── src/
│   └── package.json
├── ml-pipeline/                 # ML training pipelines
│   ├── data/
│   ├── notebooks/
│   ├── pipelines/
│   │   ├── risk_scoring/
│   │   ├── premium_pricing/
│   │   ├── trigger_prediction/
│   │   └── fraud_detection/
│   └── requirements.txt
├── infrastructure/
│   ├── docker-compose.yml
│   ├── k8s/
│   │   ├── deployments/
│   │   ├── services/
│   │   └── configmaps/
│   └── terraform/
├── docs/
│   ├── api/
│   ├── architecture/
│   └── assets/
├── .github/
│   └── workflows/
├── .env.example
├── package.json
└── README.md                    # ← You are here
```

---

## API Reference

### Worker Endpoints

```
POST   /api/v1/workers/register          # Register new worker (Aadhaar e-KYC)
GET    /api/v1/workers/:id/profile       # Get worker profile
PUT    /api/v1/workers/:id/zone          # Update worker's active zone
GET    /api/v1/workers/:id/trust-score   # Get worker's trust score
```

### Policy Endpoints

```
GET    /api/v1/policies/plans              # List available plans
POST   /api/v1/policies/subscribe          # Subscribe to a plan
PUT    /api/v1/policies/:id/pause          # Pause weekly coverage
PUT    /api/v1/policies/:id/resume         # Resume weekly coverage
GET    /api/v1/policies/:id/status         # Get policy status
```

### Claims Endpoints

```
GET    /api/v1/claims/active               # Get active claims for worker
GET    /api/v1/claims/:id                  # Get claim details
POST   /api/v1/claims/:id/appeal           # Appeal a denied claim
GET    /api/v1/claims/history              # Get claim history
```

### Trigger Endpoints

```
GET    /api/v1/triggers/active             # Get active triggers in worker's zone
GET    /api/v1/triggers/forecast           # Get predicted triggers (next 24hr)
GET    /api/v1/triggers/:id/affected-zones # Get zones affected by a trigger
```

### Partner API (for Zomato, Swiggy, etc.)

```
POST   /api/v1/partners/enroll-worker      # Bulk enroll workers
POST   /api/v1/partners/collect-premium    # Deduct premium from earnings
GET    /api/v1/partners/coverage-report    # Coverage analytics
GET    /api/v1/partners/claims-report      # Claims analytics
```

---

## Testing

```bash
# Unit tests
npm run test:unit

# Integration tests
npm run test:integration

# ML model tests
cd ml-pipeline && pytest tests/

# End-to-end tests
npm run test:e2e

# Fraud detection tests (with synthetic adversarial data)
cd services/fraud-engine && pytest tests/ -m adversarial

# Load testing (simulating 100K concurrent workers)
npm run test:load
```

---

## Deployment

### Production Deployment (AWS)

```bash
# 1. Build all service images
docker-compose -f docker-compose.prod.yml build

# 2. Push to ECR
./scripts/push-to-ecr.sh

# 3. Deploy to EKS
kubectl apply -f infrastructure/k8s/

# 4. Run smoke tests
npm run test:smoke -- --env=production
```

### Scaling Configuration

| Service | Min Replicas | Max Replicas | Scaling Metric |
|---|---|---|---|
| `trigger-monitor` | 3 | 20 | CPU > 60% |
| `claims-engine` | 3 | 50 | Queue depth > 100 |
| `payout-engine` | 2 | 30 | Queue depth > 50 |
| `fraud-engine` | 3 | 15 | Latency > 500ms |
| `ai-pricing` | 2 | 10 | CPU > 70% |

---

## Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for:

1. **Code of Conduct**
2. **Development Setup**
3. **Pull Request Process**
4. **Coding Standards**
5. **Testing Requirements**

### Key Contribution Areas

- 🌦️ **Weather Data Sources** — Integration with regional weather stations
- 🤖 **ML Models** — Improved risk scoring and fraud detection models
- 🌐 **Localization** — Additional Indian language support
- 📱 **Mobile App** — UI/UX improvements for low-end Android devices
- 🔌 **Partner Integrations** — New gig platform API connectors

---

## License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<p align="center">
  <strong>Parametrix</strong> — Because gig workers deserve a financial safety net that works as fast as they do.
</p>

<p align="center">
  Made with ❤️ for India's 15M+ delivery workers
</p>
