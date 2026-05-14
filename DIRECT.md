# GitHub Copilot Search Feature — DIRECT Demo Script
Demo goal: Show the contrast between a one-shot prompt (unmanaged) and a structured DIRECT interaction (managed).
---
## Turn 1 — Define + Inform

DIRECT: D (Define) + I (Inform) | Principle: Context-rich
PROMPT:
Referencing https://github.com/skillrepos/copilot-adv/issues/1,
read the issue and list back the acceptance criteria as you understand them.
Do not write any code yet. Wait for my approval before proceeding.
PAUSE — Human approval checkpoint. Review the list. Correct or confirm before continuing.
---
## Turn 2 — Restrict (Plan Only)
DIRECT: R (Restrict) | Principle: Bounded work
PROMPT:
Now propose a plan: which specific files will you modify and which will
you leave untouched? Scope your work to the search module and its tests only.
PAUSE — Human approval checkpoint. Confirm the file list is bounded to the search module.
---
## Turn 3 — Engineer (Implement)
DIRECT: E (Engineer) | Principles: Human accountable + Bounded work
PROMPT:
Implement the plan. Write tests that cover each acceptance criterion.
Do not modify files outside the search module.
---
## Turn 4 — Check (Verify)
DIRECT: C (Check) | Principle: Guarded
PROMPT:
Show me which test maps to which acceptance criterion.
List every file in the diff and confirm each one is in scope.
---
## Slide Reference Map
Turn 1 | Define + Inform   | Plan approved before code        | Context-rich
Turn 2 | Restrict          | Scoped to search module          | Bounded work
Turn 3 | Engineer          | Few lines, 1 module, new tests   | Human accountable
Turn 4 | Check             | Tests cover every criterion      | Guarded
---
## Unmanaged Version (contrast)
PROMPT:
Referencing the issue at https://github.com/skillrepos/copilot-adv/issues/1,
propose a diff to our Python codebase that implements the requested feature.
Result: Many lines, Multiple modules, 0 new tests
- Unrelated files reformatted
- Acceptance criteria not addressed
- No human checkpoint before implementation
