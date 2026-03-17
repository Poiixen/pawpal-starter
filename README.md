# PawPal+ (Module 2 Project)

You are building **PawPal+**, a Streamlit app that helps a pet owner plan care tasks for their pet.

## Scenario

A busy pet owner needs help staying consistent with pet care. They want an assistant that can:

- Track pet care tasks (walks, feeding, meds, enrichment, grooming, etc.)
- Consider constraints (time available, priority, owner preferences)
- Produce a daily plan and explain why it chose that plan

Your job is to design the system first (UML), then implement the logic in Python, then connect it to the Streamlit UI.

## What you will build

Your final app should:

- Let a user enter basic owner + pet info
- Let a user add/edit tasks (duration + priority at minimum)
- Generate a daily schedule/plan based on constraints and priorities
- Display the plan clearly (and ideally explain the reasoning)
- Include tests for the most important scheduling behaviors

## Getting started

### Setup

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

### Suggested workflow

1. Read the scenario carefully and identify requirements and edge cases.
2. Draft a UML diagram (classes, attributes, methods, relationships).
3. Convert UML into Python class stubs (no logic yet).
4. Implement scheduling logic in small increments.
5. Add tests to verify key behaviors.
6. Connect your logic to the Streamlit UI in `app.py`.
7. Refine UML so it matches what you actually built.

## Testing PawPal+

Run the full test suite with:

```bash
python3 -m pytest tests/test_pawpal.py -v
```

The suite covers 25 automated tests across four areas:

- **Sorting** — tasks are returned in chronological `HH:MM` order; unscheduled tasks sort last
- **Recurrence** — completing a `Daily` or `Weekly` task sets the correct `next_occurrence` date via `timedelta`; `reset()` clears it
- **Conflict detection** — duplicate start times produce warning strings; empty times and empty plans are handled without errors
- **Edge cases** — empty pet task lists, completed tasks excluded from plans, time budget enforcement, unknown pet names, and `reset_plan()` state clearing

**Confidence Level: ⭐⭐⭐⭐⭐ (5/5)**
All 25 tests pass. Core scheduling logic, recurrence math, and conflict detection are each covered by multiple independent tests including boundary conditions.

## 📸 Demo

<a href="images\app_screenshot.png" target="_blank"><img src='images\app_screenshot.png' title='PawPal App' width='' alt='PawPal App' class='center-block' /></a>
