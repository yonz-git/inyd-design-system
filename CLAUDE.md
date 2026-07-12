Behavioral guidelines to reduce common LLM coding mistakes. Merge with project-specific instructions as needed.

Tradeoff: These guidelines bias toward caution over speed. For trivial tasks, use judgment.

1. Think Before Coding Don't assume. Don't hide confusion. Surface tradeoffs. Before implementing: • State your assumptions explicitly. If uncertain, ask. • If multiple interpretations exist, present them - don't pick silently. • If a simpler approach exists, say so. Push back when warranted. • If something is unclear, stop. Name what's confusing. Ask.

2. Simplicity First Minimum code that solves the problem. Nothing speculative. • No features beyond what was asked. • No abstractions for single-use code. • No "flexibility" or "configurability" that wasn't requested. • No error handling for impossible scenarios.

3. Surgical Changes Touch only what you must. Clean up only your own mess. When editing existing code: • Don't "improve" adjacent code, comments, or formatting. • Don't refactor things that aren't broken. • Match existing style, even if you'd do it differently. • If you notice unrelated dead code, mention it - don't delete it. When your changes create orphans: • Remove imports/variables/functions that YOUR changes made unused. • Don't remove pre-existing dead code unless asked. The test: Every changed line should trace directly to the user's request.

4. Goal-Driven Execution Define success criteria. Loop until verified. Transform tasks into verifiable goals: • "Add validation" → "Write tests for invalid inputs, then make them pass" • "Fix the bug" → "Write a test that reproduces it, then make it pass" • "Refactor X" → "Ensure tests pass before and after"Design system The design system is defined by two paired files that live in the codebase: • docs/DESIGN.md — the canonical design specification, written in Google's open DESIGN.md format. This is the single source of truth for all design decisions: tokens, color, typography, spacing, layout, components, and UI patterns. • docs/DESIGN.html — a visual, rendered version of DESIGN.md so the system can be seen, not just read.

DESIGN.md is canonical and DESIGN.html mirrors it. If the two ever disagree, treat DESIGN.md as correct and bring DESIGN.html back in line.

Rules

1. Follow DESIGN.md for all frontend work. Before writing or changing any UI, read docs/DESIGN.md and build to it. Reuse the documented tokens, components, and patterns instead of inventing new ones or hardcoding values that already exist in the spec.

2. Review frontend changes against DESIGN.md and propose new patterns. After making a frontend change, compare it against docs/DESIGN.md. If you introduced anything the spec doesn't yet cover — a new component, token, pattern, or convention — surface it and propose the specific addition needed to document it. Don't silently diverge: either reuse what exists, or propose extending the spec.

3. Keep DESIGN.md and DESIGN.html consistent. The two files must always describe the same design system. Whenever you change one, update the other in the same commit so they never drift, and after editing either, verify they still match.

**These guidelines are working if:** fewer unnecessary changes in diffs, fewer regressions from overcomplication, clarifying questions come before implementation rather than after making mistakes, and no hardcoded style values appear in any diff.
