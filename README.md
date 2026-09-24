# Project Samsara

A self-recharging autonomous quadcopter; a project of the Robotics and Automation Society (RAS) at the University of Pittsburgh.

**The submitted proposal:** [`Samsara-Proposal.pdf`](Samsara-Proposal.pdf)

**Team:** Aadit Panse (Project Lead), Vybhav Reddy, Thomas Grubb, Mark Migaly, Mark Barbrak

## The goal

Samsara is a quadcopter that flies a GPS mission, lands, recharges, and takes off again with no human servicing. A remote pilot is present on every flight; "no human servicing" means that no person changes or charges the battery. The long-term goal is a drone that works over terrain with no prepared infrastructure.

Possible applications, when the full loop works:

- Persistent monitoring
- Disaster damage survey
- An aerial [Meshtastic](https://meshtastic.org/) mesh relay; a drone that recharges itself can hold a relay position, and it still relays while it sits and charges

## The plan

The project runs in stages, so that each semester ends at a useful pause point.

| Stage | Scope |
|---|---|
| **This semester** | Autonomous flight (the primary deliverable); bench test of the onboard charging electronics; a 3-4 cell solar test panel that measures real watts per kilogram |
| **Next semester** | The onboard solar array; the full land, charge, and relaunch loop; a Raspberry Pi Zero 2 W companion computer; Lua relaunch logic on the flight controller |

This semester has no ground charging pad. A pad needs a precise landing, and the onboard array makes the landing spot unimportant.

### Milestones (15 weeks)

| ID | Weeks | Milestone |
|---|---|---|
| M1 | 1-2 | Platform and compliance: inspect the old parts, order the rest, finish the legal and safety checklist |
| M2 | 3-6 | Hands-off Loiter for 3 min within a 2 m radius, on three flights; hover power measured |
| M3 | 7 | Decision gate: onboard array timing and the choice of charge controller |
| **M4** | **8-9** | **Autonomous mission: takeoff, 30 m waypoint at 10 m altitude, return, landing within 2 m, five consecutive trials** |
| M5 | 10-13 | Onboard charging electronics bench-tested and logged |
| M6 | 14-15 | Design for the onboard array and the full loop |
| M7 | 15 | Handoff package: parameters, logs, documentation, failure record (never cut) |

## The vehicle

Stock ArduPilot Copter, with no custom flight code this semester. Every part is "recommended, pending team decision".

| Block | Recommended part |
|---|---|
| Flight controller | Holybro Pixhawk 6C (2 MB flash, which Lua scripting needs) |
| Frame | Holybro X500 V2 |
| Propulsion | T-Motor Air Gear 450 II (AIR2216II 920 KV, AIR 20A ESCs, T1045 props) |
| GPS / compass | Holybro M10 |
| Power module | Holybro PM02 V3 |
| RC link | RadioMaster Pocket (ELRS) and RP1 V2 receiver |
| Telemetry | Holybro SiK V3, 915 MHz |
| Remote ID | Dronetag DRI |
| Flight battery | Tattu 4S 5200 mAh LiPo (flight tests); 4S2P Molicel P45B Li-ion (charging build) |

Estimated hover power is about 194 W with the LiPo and about 214 W with the Li-ion pack. These are estimates from the T-Motor thrust table; M2 measures the real value.

### Budget summary

All prices were listed on 2026-09-23 or 2026-09-24, before shipping and tax. Recheck each price before purchase.

| Part of the list | Cost |
|---|---|
| M4 autonomous flight | $838.62 |
| M5 charging build | $296.77 |
| M5 charge controller kit (chosen at M3) | $335.32 |
| **This semester, full list** | **$1,470.71** |

RAS committed $1,000 for this semester. Autonomous flight (M4) fits inside that amount; the charge controller kit causes most of the overage, and the M3 gate can replace it with a cheaper part.

### Safety and compliance

- Fly under FAA Part 107, with a certificated remote pilot as Pilot in Command on every flight.
- Register the aircraft and fit a Remote ID broadcast module.
- Notify the University at least 24 hours before each outdoor flight on University property (Pitt Policy RI 13).
- Follow Pitt EH&S Guideline 02-009 for lithium batteries; the team builds its own pack only with written EH&S approval.

## Repository layout

```
README.md
Samsara-Proposal.pdf     the submitted proposal
```

