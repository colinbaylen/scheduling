# Block Structure — Annual Rotation Breakdown and Shift Volumes

This document describes how the year is divided into blocks, how many residents are available per block, and how annual shift volumes are calculated.

---

## What Is a Block?

A **block** is a 2-week period during which a resident is assigned to work in a specific department or rotation. Residents rotate through different specialties (including the ED) throughout the year.

- Each block = **2 weeks**
- There are **26 two-week blocks** per year
- A resident can only be scheduled for ED shifts during blocks when they are assigned to an **ED rotation**
- Residents on off-service rotations (medicine, ICU, peds, etc.) are **not available** for ED shifts during those blocks

---

## Resident Classes and Class Sizes

| Class | Count Per Class | Total Juniors |
|-------|:--------------:|:-------------:|
| PGY1 (Intern) | 18 | — |
| PGY2 | 18 | — |
| **Junior Total** | — | **36** |

Senior class sizes are not specified in this document but follow a similar structure.

---

## PGY1 Annual Block Breakdown

PGY1s have **2 orientation blocks** at the start of their year — they **cannot be scheduled for ED shifts** during these blocks.

| Rotation | Blocks Per Year | Notes |
|----------|:--------------:|-------|
| **BH (Bellevue ED)** | 2 | ED shifts available |
| **TH (Tisch ED)** | 4 | ED shifts available |
| **Total ED Blocks** | **6** | × 18 residents = **108 blocks = 1,944 shifts** |
| BK (Brooklyn) | 2 | Off-service for juniors |
| Peds TH | 1 | Off-service |
| Peds BH | 1 | Off-service |
| Medicine | 2 | Off-service |
| MICU | 2 | Off-service |
| SICU | 2 | Off-service |
| Trauma | 2 | Off-service |
| NICU | 1 | Off-service |
| CPEP | 1 | Off-service |
| Jeopardy | 1 | Off-service |
| AnUS | 1 | Adjunct-eligible (weekends only) |
| Vacation | 2 | Not available |
| **Orientation** | **2** | **No ED shifts permitted** |

---

## PGY2 Annual Block Breakdown

| Rotation | Blocks Per Year | Notes |
|----------|:--------------:|-------|
| **BH/TH (ED)** | 11 | ED shifts available |
| **Total ED Blocks** | **11** | × 18 residents = **198 blocks = 3,564 shifts** |
| BK (Brooklyn) | 3 | Off-service for juniors |
| Peds BH | 1 | Off-service |
| Peds TH | 1 | Off-service |
| Ortho | 2 | Adjunct-eligible (weekends only) |
| AnUS | 1 | Adjunct-eligible (weekends only) |
| OB | 1 | Off-service |
| CCU | 2 | Off-service |
| Jeopardy | 1 | Off-service |
| EMS | 1 | Off-service |
| Vacation | 2 | Not available |

---

## Combined Junior ED Shift Volume

| Source | Calculation | Total |
|--------|-------------|-------|
| PGY1 ED shifts | 6 blocks/resident × 18 residents × 18 shifts/block | 1,944 shifts/year |
| PGY2 ED shifts | 11 blocks/resident × 18 residents × 18 shifts/block | 3,564 shifts/year |
| **Junior ED shifts available** | | **5,508 shifts/year** |
| **Junior ED shifts required** | 103 shifts/week × 52 weeks | **5,356 shifts/year** |
| **Surplus** | | ~152 shifts/year |

> The surplus of ~152 shifts/year can be banked as "owed shifts" or converted to optional float shifts for seniors.

---

## Per-Block Staffing Requirements

| Metric | Per Week | Per 2-Week Block |
|--------|:--------:|:----------------:|
| Required junior shifts (all sites) | 103 | 206 |
| Shifts per resident | ~9 | 18 |
| Shifts per chief | ~7 | 14 |

---

## Annual Shift Distribution by Type (Junior)

### Day Shifts
- 35 day shifts/week
- **1,820 day shifts/year**
- ~50.6 day shifts per junior resident per year

### Swing Shifts
- 35 swing shifts/week
- **1,820 swing shifts/year**
- ~50.5 swing shifts/resident per year
- *Note: Clarify with operations whether PGY1s are restricted from swing shifts*

### Night Shifts
- 33 night shifts/week
- **1,716 night shifts/year**
- Split: **30% interns (PGY1)** / **70% PGY2s**

| Level | Annual Night Shifts | Per Resident | Per Block |
|-------|:-------------------:|:------------:|:---------:|
| PGY1 | ~515 | ~28.6 | ~4.8 |
| PGY2 | ~1,201 | ~66.7 | ~6.0 |

### Weekend Shifts
- 18 weekend shifts/week
- **936 weekend shifts/year**
- ~26 weekend shifts/resident per year

---

## Adjunct-Eligible Off-Service Rotations

These rotations allow residents to work **weekend ED shifts** even while off-service. See `SCHEDULING_RULES.md` for adjunct scheduling constraints.

| Rotation | PGY Level | Adjunct Eligible |
|----------|-----------|:----------------:|
| AnUS | PGY1 and PGY2 | ✅ |
| Psych | PGY1 and PGY2 | ✅ |
| Hand | PGY1 and PGY2 | ✅ |
| Tox | PGY1 and PGY2 | ✅ (max 2 weekends/4-week block) |
| Ortho | PGY2 | ✅ (also an anchor service — anchor OSR) |

---

## Scheduling Inputs Required Per Block

When building a schedule for a given 2-week block, you need the following inputs:

1. **List of residents on ED blocks** — who is available to schedule
2. **List of OSRs** — which off-service residents are rotating through Bellevue, and whether they are anchor or non-anchor
3. **Day-off requests** — with priority ordering if more than the allotted number
4. **PGY1 site assignments** — which PGY1s are assigned to Bellevue vs Tisch
5. **Teaching shift schedule** (July–October only) — provided by UME faculty
6. **Adjunct-eligible residents** — who is on AnUS, Psych, Hand, or Tox that block

---

## Key Scheduling Numbers at a Glance

| Parameter | Value |
|-----------|-------|
| Residents per class | 18 |
| Total juniors | 36 |
| Blocks per year | 26 (2-week each) |
| Required shifts per 2-week block | 206 |
| Required shifts per week | 103 |
| Shifts per resident per block | 18 (9 per 2-week) |
| Shifts per chief per block | 14 (7 per 2-week) |
| Annual junior ED shifts required | 5,356 |
| Annual junior ED shifts available | 5,508 |
| Academic week | Sunday 00:00 – Saturday 23:59 |
| Max hours per academic week | 60 |
| Min rest between shifts | Equal to shift duration |
| Max shift length | 12 hours |
