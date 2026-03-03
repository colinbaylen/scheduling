# Hard Constraints — Duty Hours and Inviolable Rules

These rules MUST NOT be violated under any circumstances. Any schedule that breaks these rules is invalid.

---

## 1. Academic Week Definition

- The academic week begins at **Sunday 00:00** and ends **Saturday 23:59**.
- EM blocks run Monday–Sunday.
- **Critical**: Even if a resident is starting an EM block on Monday, any hours they worked on the preceding Sunday count toward that academic week's duty hours.

---

## 2. Maximum Hours Per Week

- No resident may work more than **60 hours in a single academic week**.
- All shifts within the Sunday–Saturday window are counted, regardless of when the block started.

---

## 3. Required Time Off Between Shifts

- A resident must have **at least the same number of hours off** as the duration of the shift they just completed before starting their next shift.
  - Example: A resident who works a **12-hour shift** must have at least **12 hours off** before their next shift begins.
  - Example: A resident who works a night shift ending at **8:00 AM** cannot start a day shift at **8:00 AM** — they must wait until at least **8:00 PM** to start.
- This rule applies to all shift transitions regardless of day of week.

---

## 4. Maximum Continuous Hours

- No resident may work more than **12 hours straight** in the Emergency Department.
- This effectively caps all ED shifts at 12 hours maximum.

---

## 5. Minimum 24-Hour Rest Period Per Week

- Each resident must have at least **one full 24-hour period off** within each academic week (Sunday–Saturday).

---

## 6. Maximum Shifts Per Block

- Standard residents: maximum **9 shifts per 2-week block** (18 per 4-week block).
- Chief residents: maximum **7 shifts per 2-week block** (14 per 4-week block).
- Scheduling more than the maximum is not permitted, except to create "owed shifts" or float shifts when coverage has already been met for all required slots.

---

## 7. Shift Eligibility — PGY Level and Role

- Shifts have explicit eligibility requirements by PGY level. Assigning a resident to a shift they are not eligible for is invalid.
- See `RESIDENT_ELIGIBILITY.md` for the full matrix of shift eligibility by PGY and anchor status.

### Key Hard Eligibility Rules:
- **PGY4 only**: Bellevue Team 2 senior shifts (`D2a`, `D2p`, `N2`)
- **PGY2 only**: Bellevue `d2a`, `n1`, `n3`, and `d2b` on Wednesdays
- **PGY2 required**: At least one PGY2 must staff Team 2 day shift at Bellevue (the examining resident role); this applies on weekdays and weekends
- **PGY2 required**: On every Bellevue night shift, there must be a PGY2 on Team 1 AND a PGY2 on Team 3
- **Non-anchor only**: Non-anchor OSRs (Psych, OMFS, Ophthalmology) may ONLY staff Team 2 non-anchor designated shifts; they cannot staff any other junior shift
- **Anchor required**: All shifts not explicitly labeled NON-ANCHOR must be staffed by anchor residents

---

## 8. Site Restrictions (Hard)

- **PGY1 (Intern)**: Assigned to a single specific site (either Bellevue or Tisch) for the duration of a block. May occasionally have a small number of shifts at the other site, but should be primarily at their assigned site.
- **PGY2**: Can work shifts at either Bellevue or Tisch within a block, but NOT Brooklyn during a junior block.
- **PGY3 and PGY4**: Can work at Bellevue, Tisch, or Brooklyn during an EM block.
- **Off-Service Rotators (OSRs)**: Only work at Bellevue. They do NOT staff Tisch or Brooklyn shifts.

---

## 9. Adjunct Shift Hard Limits

- Adjunct shifts (for residents on AnUS, Psych, Hand, Tox rotations) may only be scheduled on **weekends** — never weekdays.
- Maximum **1 adjunct shift per resident per weekend** (they can work multiple weekends in a block, but not both days of the same weekend).
- Tox adjunct residents: maximum **2 weekends** in a 4-week block.

---

## 10. Wednesday Blackout

- No residents may be scheduled for morning shifts on Wednesdays due to protected academic conferences.
- On Wednesdays, only **afternoon and evening shifts** are permitted (1p onwards).
- See `SCHEDULING_RULES.md` for the full Wednesday staffing model.

---

## Constraint Summary Table

| Rule | Threshold | Applies To |
|------|-----------|-----------|
| Max hours/week | 60 hours | All residents |
| Min rest between shifts | = hours just worked | All residents |
| Max consecutive hours | 12 hours | All residents |
| Min days off/week | 1 full 24-hour period | All residents |
| Max shifts/2-week block | 9 (resident), 7 (chief) | All |
| PGY4-only shifts | D2a, D2p, N2 at BH | Seniors |
| PGY2-required shifts | d2a, n1, n3, Wed d2b at BH | Juniors |
| Non-anchor only | Team 2 non-anchor shifts | OSR non-anchors |
| PGY1 site lock | Assigned site only (mostly) | PGY1 |
| OSR site lock | Bellevue only | OSRs |
| Adjunct — weekday ban | Weekends only | Adjunct residents |
| Adjunct — per weekend | Max 1 shift/resident/weekend | Adjunct residents |
| Tox adjunct | Max 2 weekends/block | Tox adjunct residents |
| Wednesday morning | No shifts before ~1pm | All residents |
