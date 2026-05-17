---
marp: true
theme: default
paginate: true
size: 16:9
header: "Cargo-to-Door | Autonomous Last-Meter Logistics"
footer: "Draft v0.1"
style: |
  section { font-size: 22px; }
  h1 { color: #1f3a5f; }
  h2 { color: #1f3a5f; }
  .placeholder { color: #b00; font-style: italic; }
  .columns { display: grid; grid-template-columns: 1fr 1fr; gap: 1.2rem; }
  .columns-3 { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 0.8rem; }
  table { font-size: 18px; }
  section.title h1 { font-size: 56px; margin-bottom: 0.2em; }
  section.title h3 { color: #555; font-weight: 400; }
  section.section-divider { background: #1f3a5f; color: white; text-align: center; }
  section.section-divider h1 { color: white; font-size: 64px; }
---

<!-- _class: title -->
<!-- _paginate: false -->

# Cargo-to-Door

### Autonomous Last-Meter Delivery for Vertical Cities

A building-integrated logistics platform for new high-rises **and** historic retrofits.

<span class="placeholder">[placeholder] Presented by: Team Name — PI, Co-PI, Members — Institution — Date</span>

---

## Agenda

1. **Background**
   - Motivation & Problem Definition
   - Literature Survey: state of the art, our proposed solution, breakthrough technologies

2. **The Team & Innovative Product Development**
   - Team & capabilities, requirements, architecture, design, implementation, testing

3. **Roadmap / Project Plan**
   - Milestones, deliverables, work packages, timeline

4. **Commercialization & Business Model**
   - Market, competition, budget, risks

---

<!-- _class: section-divider -->

# Part 1 — Background

---

## Motivation & Problem Definition

- **Last-mile is the broken link.** It accounts for ~30–50% of total e-commerce logistics cost and a disproportionate share of urban congestion and emissions.
- **The "last-meter" problem.** Even when a parcel reaches a building lobby, the journey from front-door to apartment-door is manual, slow, and unreliable.
- **Failed deliveries & porch piracy.** Missed handoffs and unattended parcels drive return-rates, theft, and customer churn.
- **Vertical density breaks current solutions.** Drones cannot land on every balcony; sidewalk rovers cannot ride elevators; couriers cannot scale to 50-storey towers.
- **Heritage constraints.** Protected and historic buildings cannot be torn open for new logistics infrastructure — yet their residents demand the same service level.

> Goal: a continuous, autonomous, weatherproof path from the sky (or sidewalk) to the resident's door — in both new construction and historic retrofits.

---

## Literature Survey — Past Solutions / State of the Art

| Approach | Examples | Strengths | Limitations |
|---|---|---|---|
| Drone-to-doorstep | Wing, Zipline, Matternet | Bypasses ground congestion | Needs landing pad; weather-sensitive; one parcel per flight; not vertical-city friendly |
| Sidewalk micro-rovers | Starship, Serve, Coco | Low-cost, social-friendly | Stuck at the lobby; no vertical access; theft risk |
| Parcel-locker arrays | Amazon Hub, InPost | Secure, asynchronous pickup | Still requires resident trip; ground-floor only |
| Pneumatic / vacuum tubes | Hospital legacy, Hyperloop-cargo concepts | Weather-immune, high throughput | Single-routing; expensive retrofit; small payload |
| In-building robotics | Relay, Savioke | Door-to-door inside building | Needs elevator integration; no exterior link |

**Gap:** no end-to-end system spans *airspace → building skin → vertical core → resident door*, and none retrofits gracefully onto protected architecture.

---

## Proposed Solution & Innovation

![bg right:45%](images/new-building-rooftop.png)

**Two parallel tracks, one platform:**

- **New builds — Rooftop *Flight Deck* + internal vertical shaft.**
  Drones *hover and winch-drop* into an open aerodynamic catchment funnel — no landing required.
- **Historic builds — *Exo-Logistics Spine*.**
  A modular, exterior pneumatic-decelerator tube clipped to the facade, feeding automatic floor-switchers inside.
- **Passive-logistics philosophy.** Gravity chutes, motorized rollers, mechanical diverters and claws replace expensive robotic arms wherever possible.
- **Multi-modal intake.** The same vertical core accepts both *aerial drone* and *sidewalk micro-rover* deliveries.

---

## Breakthrough Technologies Required

- **Hover-and-winch package drop** — drone holds altitude `Z` while lowering a parcel; controller compensates for wind and tether sway.
- **Aerodynamic catchment funnel + S-Trap drainage** — captures off-center drops, lets rain through, blocks rain from following the parcel.
- **Pneumatic decelerator tube** — variable-pressure exterior shaft that slows a free-falling parcel from terminal velocity to safe handoff speed.
- **Automatic floor-switcher** — passive-actuated diverter that routes packages into the correct resident's intake chamber.
- **Micro-rover ↔ kinetic docking hatch** — standardized mechanical/data interface so any six-wheeled rover can offload into the building.
- **Building-level airspace orchestration** — scheduling, geofencing, and conflict-resolution for multiple drones over a single rooftop.

---

<!-- _class: section-divider -->

# Part 2 — Team & Innovative Product

---

## The Team & Capabilities

<span class="placeholder">[placeholder] — fill with real names, affiliations, and CVs before submission.</span>

| Role | Person | Capability brought |
|---|---|---|
| Principal Investigator | <span class="placeholder">[name]</span> | Systems engineering, autonomous vehicles |
| Mechanical Lead | <span class="placeholder">[name]</span> | Aerodynamic structures, pneumatic systems |
| Controls & Robotics | <span class="placeholder">[name]</span> | Drone control, robotic manipulation |
| Software & Cloud | <span class="placeholder">[name]</span> | Fleet orchestration, edge computing |
| Architecture & Civil | <span class="placeholder">[name]</span> | High-rise integration, historic-preservation retrofits |
| Business & Regulatory | <span class="placeholder">[name]</span> | Go-to-market, FAA / municipal liaison |

**Institutional capabilities:** wind-tunnel access, drop-test rig, full-scale mockup hall, partnership LOIs with <span class="placeholder">[developer]</span> and <span class="placeholder">[historic-district BID]</span>.

---

## Innovative Product / Process Development — Overview

```mermaid
flowchart LR
  Drone[Autonomous Drone] --> Hub[Rooftop Flight Deck]
  Hub --> Funnel["Catchment Funnel + S-Trap"]
  Funnel --> Sort[Internal Sorting Shaft]
  Sort --> Dumb[Smart Dumbwaiter]
  Dumb --> Locker[Floor Smart-Locker]
  Locker --> Resident
  Rover[Six-Wheeled Micro-Rover] --> Hatch[Kinetic Docking Hatch]
  Hatch --> Arm[Ceiling Robotic Arm]
  Arm --> Sort
  Cloud[Cloud Orchestration] -.-> Drone
  Cloud -.-> Rover
  Cloud -.-> Locker
```

Two intake modalities (sky + street) converge on a single internal sorting core that distributes to resident smart-lockers — orchestrated by the cloud layer.

---

## Requirements Definition & Analysis

**Functional**

- Throughput: <span class="placeholder">[≥ 60 pkg/hr per building peak]</span>
- Payload envelope: <span class="placeholder">[≤ 5 kg, ≤ 40 × 30 × 30 cm]</span>
- End-to-end latency drone-arrival → locker: <span class="placeholder">[< 4 min]</span>

**Non-functional**

- Weatherproof to <span class="placeholder">[IP65 equivalent]</span>; operable in <span class="placeholder">[wind ≤ 12 m/s, rain ≤ 25 mm/h]</span>
- Acoustic limit at facade: <span class="placeholder">[≤ 55 dBA at 10 m]</span>
- Fire-rating of internal shafts: <span class="placeholder">[≥ 2-hour]</span>

**Regulatory / safety**

- FAA Part 107 (or local equivalent) drone operations
- Local building, fire, and (for retrofits) landmark-commission codes

**UX**

- Resident retrieval time at locker: <span class="placeholder">[< 30 s]</span>; mobile app notify within <span class="placeholder">[10 s of locker close]</span>

---

## High-Level System Architecture

```mermaid
flowchart TB
  subgraph airspace [Airspace Layer]
    DroneFleet[Drone Fleet]
    ATC["Airspace Control / Geofence"]
  end
  subgraph rooftop [Rooftop Hub]
    FlightDeck[Flight Deck]
    CatchFunnel["Catchment Funnel + S-Trap"]
  end
  subgraph core [Vertical Core]
    SortShaft[Sorting Shaft]
    Dumbwaiter[Smart Dumbwaiter]
  end
  subgraph floor [Floor Distribution]
    Switcher[Automatic Floor Switcher]
    LockerArray[Smart-Locker Array]
  end
  subgraph street [Street Layer]
    Rover[Micro-Rover]
    Hatch[Kinetic Docking Hatch]
    Vestibule["Vestibule + Robotic Arm"]
  end
  subgraph cloud [Cloud Orchestration]
    Fleet[Fleet Manager]
    Routing[Routing & Scheduling]
    ResidentApp[Resident App]
  end

  DroneFleet --> FlightDeck --> CatchFunnel --> SortShaft --> Dumbwaiter --> Switcher --> LockerArray
  Rover --> Hatch --> Vestibule --> SortShaft
  ATC -.-> DroneFleet
  Fleet -.-> DroneFleet
  Fleet -.-> Rover
  Routing -.-> Switcher
  ResidentApp -.-> LockerArray
```

---

## Design — Rooftop Flight Deck

![bg right:55%](images/new-building-rooftop.png)

- **Stable delivery zone** with perforated wind-break louvers to tame rooftop turbulence.
- **Aerodynamic catchment funnel** sized for off-center hover drops.
- **Secure storage lockers** for high-value or oversized parcels awaiting retrieval.
- **Hover-winch protocol**: drone holds altitude `Z`, lowers parcel through funnel mouth, releases tether — never lands.
- **Flight-path corridor** geofenced into building airspace; multiple drones serialized on approach.

---

## Design — Drop Funnel & S-Trap Drainage

![bg right:55%](images/new-building-get-cargo.png)

- **Drone drop aperture** with **Teflon-grated** inner skin — parcel slides, water passes through.
- **U-bend / S-Trap mechanism** — passive drainage; rainwater diverts to the storm drain, parcel continues down the *Momentum Carry Zone*.
- **Dry interior zone** opens onto the **autonomous internal sorting shaft** and roller conveyor.
- Solves the rain-in-shaft constraint called out in `content.md` — *no* powered seals, *no* moving water doors.

---

## Design — Internal Sorting Core

![bg right:55%](images/new-building-seperator.png)

- **Stainless-steel gravity chute** delivers parcels from the rooftop core to floor-level receiving bays.
- **Motorized roller conveyor + diverter flaps** route each parcel to its destination column.
- **Smart dumbwaiter** (open-front car in a dedicated shaft) lifts/lowers to the resident's floor.
- Embodies the **passive-logistics** principle from `content.md`: gravity + rollers + mechanical diverters in place of robotic arms.

---

## Design — Resident Smart-Locker Array

![bg right:55%](images/new-building-smart-locker.png)

- **Integrated smart-locker array** built into the apartment-floor hallway wall — wood facade, glass + tech inserts.
- **Sliding secure logistics core** behind the lockers connects directly to the vertical shaft.
- Resident receives push notification (*"Package received: Unit 4C, Compartment L16"*), authenticates at the screen, locker opens.
- Inset schematic on the source drawing details the automated dispatch path: internal chute → conveyor sorting → dumbwaiter shaft.

---

## Design — Retrofit "Exo-Logistics Spine"

![bg right:50%](images/retrofit-pipe-design-switcher.png)

- **Exterior modular tube** clamped to the facade of historic buildings — no structural intervention to the protected envelope.
- **Pneumatic decelerator** inside the tube progressively brakes a free-falling parcel.
- **Automatic switcher mechanism** (right inset) diverts the parcel into each floor's **resident intake chamber**.
- Rooftop **drone docking station** caps the spine; a drone lowers the parcel into the tube mouth.
- Honors the heritage facade while delivering modern logistics capability.

---

## Design — Ground-Level Micro-Rover Interface

![bg left:50%](images/new-building-rover.png)
![bg right:50%](images/new-building-rover-get.png)

- **Segregated micro-logistics lane** along the sidewalk; rover approaches the **kinetic docking hatch** in the facade.
- Inside the vestibule, a **ceiling-mounted precision robotic arm** lifts parcels off the rover's open cargo bin onto a **motorized roller conveyor** that joins the internal sorting shaft.
- Retrofit equivalent: **street-level micro-vestibule** with a telescoping claw + motorized lift-tray (see `images/retrofit-claw.png`).
- Implements the *sidewalk-rover pivot* called out in `content.md`.

---

## Implementation & Testing

**Prototyping plan**

1. **Subscale rooftop funnel** + instrumented drop rig — characterize capture cone vs. wind speed.
2. **Single-floor mockup** of internal sorting + smart-locker — measure throughput and jam rate.
3. **Exo-Spine pilot section** (3 storeys) on a non-occupied historic structure — validate pneumatic deceleration and switcher routing.
4. **Rover ↔ hatch integration** with a partner micro-rover OEM.

**Test KPIs** <span class="placeholder">[placeholder targets]</span>

| KPI | Target |
|---|---|
| Drop capture success rate | <span class="placeholder">≥ 99.5%</span> |
| Mean time, rooftop → locker | <span class="placeholder">≤ 3 min</span> |
| Facade acoustic level | <span class="placeholder">≤ 55 dBA @ 10 m</span> |
| Rain ingress past S-Trap | <span class="placeholder">0 ml/h @ 25 mm/h rainfall</span> |
| Rover handoff cycle time | <span class="placeholder">≤ 45 s</span> |

---

<!-- _class: section-divider -->

# Part 3 — Roadmap / Project Plan

---

## Roadmap / Project Plan

<span class="placeholder">[placeholder] — 24-month phased plan, refine with real funding milestones.</span>

| Phase | Months | Focus | Exit gate |
|---|---|---|---|
| **P1 — R&D** | 1–4 | Concept refinement, simulation, safety case | Design review #1 |
| **P2 — Subsystem prototypes** | 5–10 | Funnel, S-Trap, switcher, hatch, rover dock | Bench-test sign-off |
| **P3 — Integrated single-floor pilot** | 11–16 | New-build mockup + Exo-Spine 3-storey rig | End-to-end KPI demo |
| **P4 — Certification & approvals** | 17–20 | FAA waiver, fire & building code, landmark commission | Permits granted |
| **P5 — Commercial pilot** | 21–24 | One new-build tower + one retrofit block | Paying first customer |

---

## Milestones, Deliverables & Work Packages

<span class="placeholder">[placeholder] — owners and exact months TBD.</span>

| WP | Title | Key deliverables | Lead | Month |
|---|---|---|---|---|
| WP1 | Rooftop Hub | Flight Deck mock-up, hover-drop protocol spec | <span class="placeholder">[name]</span> | M8 |
| WP2 | Vertical Core | Sorting-shaft prototype, dumbwaiter integration | <span class="placeholder">[name]</span> | M12 |
| WP3 | Exo-Spine | Pneumatic-tube section, automatic switcher | <span class="placeholder">[name]</span> | M14 |
| WP4 | Rover Interface | Kinetic docking hatch + robotic-arm vestibule | <span class="placeholder">[name]</span> | M12 |
| WP5 | Software & Orchestration | Fleet manager, resident app, routing engine | <span class="placeholder">[name]</span> | M16 |
| WP6 | Regulatory & Safety | FAA waiver, fire/building/landmark approvals | <span class="placeholder">[name]</span> | M20 |
| WP7 | Pilot Deployment | One new-build + one retrofit operating | <span class="placeholder">[name]</span> | M24 |

---

## Task Allocation & Timeline

```mermaid
gantt
  title 24-month Project Timeline (placeholder)
  dateFormat  YYYY-MM-DD
  axisFormat  M%m
  section WP1 Rooftop Hub
  Concept & sim         :a1, 2026-06-01, 90d
  Funnel prototype      :a2, after a1, 120d
  section WP2 Vertical Core
  Sort-shaft design     :b1, 2026-07-01, 90d
  Mock-up build         :b2, after b1, 120d
  section WP3 Exo-Spine
  Pneumatic tube R&D    :c1, 2026-09-01, 120d
  Switcher prototype    :c2, after c1, 90d
  section WP4 Rover Interface
  Hatch & arm           :d1, 2026-08-01, 150d
  section WP5 Software
  Fleet manager         :e1, 2026-06-01, 240d
  Resident app          :e2, 2027-01-01, 180d
  section WP6 Regulatory
  FAA waiver            :f1, 2027-04-01, 180d
  Fire / landmark       :f2, 2027-04-01, 180d
  section WP7 Pilot
  New-build pilot       :g1, 2027-10-01, 120d
  Retrofit pilot        :g2, 2027-10-01, 120d
```

---

<!-- _class: section-divider -->

# Part 4 — Commercialization & Business Model

---

## Market Analysis

**Target market**

- Luxury high-rise residential developers (new construction)
- Smart-city districts and master-planned communities
- Historic-district Business Improvement Districts (BIDs) commissioning the Exo-Spine retrofit
- Mixed-use towers with concierge service expectations

**Customer profile**

- Developer / building owner buys the infrastructure; residents are the end users.
- Logistics providers (Amazon, FedEx, UPS, local couriers) are channel partners paying per-delivery.

**Bureaucracy & approvals**

- FAA Part 107 + local airspace authority
- Building & fire code (UL listing for shafts)
- Landmark / historic-preservation commissions (retrofit only)

**Market size** <span class="placeholder">[placeholder]</span>

- TAM: <span class="placeholder">$XX B</span> global vertical-living logistics
- SAM: <span class="placeholder">$X B</span> Tier-1 cities with drone-friendly regs
- SOM (Year 5): <span class="placeholder">$XXX M</span>

**Marketing & growth strategy**

- Lighthouse pilot with one flagship developer → case study → master-developer agreements.
- "Logistics-ready building" certification co-marketed with developers.
- API partnerships with major carriers for instant scale on Day 1 of a building going live.

---

## Competitor Analysis

| Competitor | Their play | Where we win |
|---|---|---|
| **Wing / Zipline / Matternet** | Drone-to-doorstep delivery | We solve the *last-meter* (lobby→door); they stop at the curb / yard |
| **Starship / Serve / Coco** | Sidewalk micro-rovers | We *integrate* with their rovers via a standard hatch — we are the building-side complement, not a competitor |
| **Amazon Hub / InPost** | Ground-floor parcel lockers | Our smart-lockers are *on the resident's own floor*, fed automatically — no lobby trip |
| **Relay / Savioke** | In-building delivery robots | We bypass elevators with a dedicated shaft; lower opex, higher throughput |
| **Pneumatic-tube vendors** | Hospital-grade tubes | We add aerial intake, weather handling, and resident-locker layer |

**Our competitive advantage**

- **Only end-to-end, building-integrated** stack from airspace to apartment door.
- **Weatherproof passive shafts** — no powered seals to fail.
- **Retrofit option** (Exo-Spine) unlocks the entire historic-building market that no competitor addresses.
- **Modality-agnostic** — same core serves drones, rovers, and human couriers.

---

## Budget, Pricing & Monetization

**Cost structure** <span class="placeholder">[placeholder]</span>

| Line | Year 1 | Year 3 |
|---|---|---|
| R&D / engineering | <span class="placeholder">$X M</span> | <span class="placeholder">$X M</span> |
| Hardware (per-building install) | <span class="placeholder">$XXX k</span> | <span class="placeholder">$XXX k</span> |
| Software / cloud | <span class="placeholder">$X M</span> | <span class="placeholder">$X M</span> |
| Operations & support | <span class="placeholder">$X M</span> | <span class="placeholder">$X M</span> |

**Pricing models**

- **Capex sale** of the in-building infrastructure to developers (new construction) or BIDs (retrofit).
- **SaaS** orchestration fee per building per month — <span class="placeholder">$X k/mo</span>.
- **Per-delivery fee** charged to logistics partners — <span class="placeholder">$X.XX per parcel</span>.
- **Premium-resident subscription** for guaranteed time-slots and oversized-parcel handling.

**Unit economics** <span class="placeholder">[placeholder]</span>

- Payback per building: <span class="placeholder">~XX months</span>
- Gross margin at scale: <span class="placeholder">~XX%</span>

---

## Challenges & Business Risks

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Urban drone-airspace regulation slips | High | High | Early FAA waiver process; partner with city pilot programs |
| Public acceptance (noise, privacy, "drones overhead") | Med | High | Acoustic engineering at facade; opt-in resident comms; community design reviews |
| Insurance & liability for sky-dropped parcels | Med | Med | Capped payload, redundant tether, geofenced corridor, partner with logistics-insurance underwriter |
| Landmark-commission rejection of Exo-Spine | Med | High | Reversible / non-penetrating clamps; engage preservation architects from day 1 |
| Weather window too narrow (wind, ice, lightning) | Med | Med | Hybrid sky + street modality — rovers cover the window where drones can't fly |
| Hardware reliability (jammed switcher, frozen rollers) | Med | Med | Passive-mechanical design philosophy; predictive maintenance via cloud telemetry |
| Capital intensity / long sales cycle to developers | High | Med | SaaS layer for recurring revenue; lighthouse-pilot case-study to compress sales cycle |

---

<!-- _class: title -->
<!-- _paginate: false -->

# Thank You

### Questions & Discussion

<span class="placeholder">[placeholder] contact: team@cargo-to-door.example | project repo: github.com/&lt;org&gt;/cargo-to-door-design</span>
