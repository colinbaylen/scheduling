# EM Residency Scheduling System

## Project Purpose

This documentation describes the rules, constraints, and shift structures needed to build an automated scheduling system for Emergency Medicine (EM) resident doctors across three hospital sites. The scheduler must assign residents to shifts across a 2-week or 4-week block while satisfying hard duty-hour constraints, eligibility rules, staffing requirements, and soft preferences.

---

## File Index

| File | Contents |
|------|----------|
| `README.md` | This file — overview, glossary, and system summary |
| `HARD_CONSTRAINTS.md` | Inviolable duty-hour and legal scheduling rules |
| `SCHEDULING_RULES.md` | Soft rules, preferences, special cases (Wednesdays, adjuncts, float shifts, golden weekends, requests) |
| `RESIDENT_ELIGIBILITY.md` | Who can work which shifts — PGY level, site, and anchor/non-anchor restrictions |
| `SHIFT_CATALOG.md` | Every named shift with exact start/end times, organized by site and PGY level |
| `STAFFING_REQUIREMENTS.md` | Required shift coverage per team per day of week at Bellevue and Tisch |
| `BLOCK_STRUCTURE.md` | Annual block breakdown, class sizes, and shift volume totals |

---

## Glossary / Abbreviations

| Term | Definition |
|------|-----------|
| EM | Emergency Medicine |
| PGY | Post-Graduate Year — the year of residency (PGY1 through PGY4) |
| Intern | PGY1 resident |
| Junior | PGY1 or PGY2 resident |
| Senior | PGY3 or PGY4 resident |
| Chief | Senior-level chief resident; scheduled for 7 shifts/2-week block (14/4-week block) |
| OSR | Off-Service Rotator — a resident from another specialty temporarily rotating through the ED |
| Block | A 2-week (or occasionally 4-week) period during which a resident is assigned to the ED |
| BH / BK | Bellevue Hospital / Brooklyn Hospital |
| TH | Tisch Hospital (also referred to as NYU) |
| Kimmel | Kimmel pavilion at NYU/Tisch, associated with Team 2 (Red Team) |
| Golden Weekend | A full Saturday and Sunday both off within the same week |
| WC | Wildcard shift — a Wednesday-only, non-team-specific shift at Tisch (1p–9p) |
| DF | Day Float — a Bellevue senior float shift (8a–4p weekdays, 12p–8p Wednesdays) |
| TF | Tisch Float — a Tisch senior float shift (8a–4p) |
| KF | Kimmel Float — a Kimmel float shift |
| DT | Bellevue Teaching Shift (8a–4p), for senior residents aligned with medical students |
| TT | Tisch Teaching Shift (8a–4p), same purpose |
| PES | Pediatric Emergency Service (at Bellevue peds) |
| PECC | Pediatric Emergency Care Center (at Tisch peds) |
| Anchor | Resident from EM, Ortho, Internal Medicine, or Plastic Surgery — can staff any junior shift |
| Non-Anchor | Resident from Psych, OMFS, or Ophthalmology — can only staff Team 2 non-anchor shifts |
| Adjunct | ED shifts worked by residents on specific off-service rotations (AnUS, Psych, Hand, Tox) |
| LMR | Likely "Learning Morning Report" — the d2a PGY2 at Bellevue is expected to attend |
| Morning Report | Academic conference attended by D2a PGY4 on M/T/Th/Fr (denoted in pink) |

---

## High-Level Scheduling Summary

### Shift Volumes per Resident
- **Standard resident**: 9 shifts per 2-week block (18 per 4-week block)
- **Chief resident**: 7 shifts per 2-week block (14 per 4-week block)
- Extra shifts beyond required coverage may be banked as "owed shifts" or assigned as float shifts (DF/KF) for seniors

### Shift Lengths
| Resident Type | Weekday Shift | Weekend Shift |
|---------------|--------------|--------------|
| PGY1 (Junior) | 10 hours | 12 hours |
| PGY2 (Junior) | 10 hours | 12 hours |
| PGY3 (Senior) | 10 hours | 10 hours |
| PGY4 (Senior) | 8 hours | 8 hours |
| All Brooklyn   | 10 hours | 10 hours (regardless of PGY) |

### Naming Convention
- **Lowercase** shift names = junior shifts (e.g., `d2a`, `n1`, `k2b`)
- **UPPERCASE** shift names = senior shifts (e.g., `D2a`, `N2`, `T1a`)

### Academic Week
- Starts: Sunday 00:00
- Ends: Saturday 23:59
- EM blocks run Monday–Sunday; Sunday hours count toward the current academic week's duty hours

### Sites
- **Bellevue (BH)**: Primary site with 5 teams on weekdays, 3 teams on nights/weekends
- **Tisch/NYU (TH)**: Secondary site with 2 teams
- **Brooklyn (BK)**: Third site, seniors and PGY2s only

---

## Manual Scheduling Algorithm (Annaliese's Method)

The following order-of-operations is recommended for building a schedule:

1. Confirm the list of off-service rotators (OSRs) for the block
2. Record all resident day-off requests
3. Staff the most constrained shifts first:
   - PGY2 night shifts (n1/n3 at Bellevue)
   - Non-anchor resident shifts
   - Examining resident shifts (PGY2 on Team 2 day)
4. Fill all night shifts and weekend shifts
5. Fill remaining day shifts (plug-and-play)
6. Check counters to ensure no shifts are left unstaffed
7. Audit for duty hour violations
