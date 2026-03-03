# Schedule Generation Guide (Template-Preserving)

The scheduler now uses the Block 9 workbook as the **exact formatting template** (colors, cell styles, spacing, merged cells, sheet layout), and generates a Block 10 schedule by assigning current residents to that template structure.

## Files Used

- `/Users/colin/Library/Mobile Documents/com~apple~CloudDocs/cbproj/scheduling/Example/block 9 output.xlsx`
  - Formatting and layout template.
- `/Users/colin/Library/Mobile Documents/com~apple~CloudDocs/cbproj/scheduling/25-26 schedule.xlsx`
  - Resident block availability (`9B`, `10A`, `10B`, `11A`).
- `/Users/colin/Library/Mobile Documents/com~apple~CloudDocs/cbproj/scheduling/Test/block 10 data.xlsx`
  - Off-service rotators (OSRs).
- `/Users/colin/Library/Mobile Documents/com~apple~CloudDocs/cbproj/scheduling/Test/block 10 OSRs.xlsx`
  - Preferred OSR input (if present). Includes `Availability` date ranges.
- `/Users/colin/Library/Mobile Documents/com~apple~CloudDocs/cbproj/scheduling/Test/SAMN Block 10 Request Form (Responses)  (claude test).xlsx`
  - Day-off requests.
- `/Users/colin/Library/Mobile Documents/com~apple~CloudDocs/cbproj/scheduling/Test/block 10 scheduling requests.xlsx`
  - Preferred scheduling request input (if present).
- `/Users/colin/Library/Mobile Documents/com~apple~CloudDocs/cbproj/scheduling/generate_schedule.py`
  - Generator.

## Output

- `/Users/colin/Library/Mobile Documents/com~apple~CloudDocs/cbproj/scheduling/Test/block 10 generated schedule.xlsx`

This output preserves the same sheet structure as the Block 9 template:
- `BHTH`
- `PGY1`
- `PGY2`
- `PGY3`
- `PGY4`
- `OSRs`

## What Is Now Included

- Junior scheduling: OSR + PGY1 + PGY2
- Senior scheduling: PGY3 + PGY4
- Request-aware matching (penalizes requested-off violations)
- Role/eligibility checks during row-pattern assignment
- OSR availability windows from OSR input are enforced as hard constraints
- OSR scheduling requests from the request-form file are applied in addition to OSR availability windows
- Block 10 headers/dates updated in the `BHTH` sheet

## How It Preserves Formatting

- Starts from `Example/block 9 output.xlsx`
- Keeps existing sheet layout and style model intact
- Writes Block 10 resident names/IDs and assignments into template structure
- Keeps the template’s shift-cell pattern/formatting while remapping residents

## Run

```bash
python3 generate_schedule.py
```

Default file selection now prefers renamed files when present:
- Template: `Example/block 9 schedule.xlsx` (fallback `Example/block 9 output.xlsx`)
- OSR input: `Test/block 10 OSRs.xlsx` (fallback `Test/block 10 data.xlsx`)
- Requests: `Test/block 10 scheduling requests.xlsx` (fallback prior Google Form filename)

Optional:

```bash
python3 generate_schedule.py \
  --template "Example/block 9 output.xlsx" \
  --roster "25-26 schedule.xlsx" \
  --osr "Test/block 10 data.xlsx" \
  --requests "Test/SAMN Block 10 Request Form (Responses)  (claude test).xlsx" \
  --output "Test/block 10 generated schedule.xlsx"
```

## About OpenAI API vs Deterministic Engine

Best practice remains:
- Deterministic code for assignment + constraints + export
- OpenAI API for request parsing/cleanup, conflict explanations, and optional UI guidance

For a production web app, use deterministic scheduling as the core backend and optionally call OpenAI for input normalization and user-facing explanations.
