# Code Review And Consolidation

## Purpose
Review project code to establish current status, remove duplicated logic, integrate equivalent behavior into canonical paths, and eliminate obsolete features/functions safely.

## Required Outcomes
- Clear current project status summary.
- Duplicate logic identified and consolidated.
- Obsolete features/functions hard-removed by default after validation.
- Regression risk validated with targeted tests.

## Policy Defaults
- Default: auto-refactor duplicate logic immediately into a canonical path.
- Default: hard-remove obsolete functions/features once replacement behavior is validated.
- Exception: if blast radius is high, propose a short consolidation plan first and execute after approval.

## Workflow
1. Build current status snapshot.
- Review recent commits and changed files.
- Identify active risk areas and unresolved failures.

2. Perform duplicate-logic review.
- Search for same business rule implemented in multiple files.
- Select one canonical implementation.
- Auto-refactor callers to canonical path immediately by default.

3. Remove obsolete behavior.
- Identify dead code, replaced functions, and stale feature branches.
- Hard-remove unused paths when replacement is verified.
- If immediate removal is high-risk, propose consolidation plan first as an approved exception.

4. Validate behavior.
- Run targeted unit/integration tests for affected modules.
- Compare critical outputs before/after consolidation.

5. Report decisions.
- List integrated duplicates.
- List removed obsolete functions/features.
- List any deferred removals with rationale.

## Quality Gates
- No functional regression in covered tests.
- No duplicate canonical logic remains for reviewed scope.
- No obsolete function remains undocumented.

## Enforcement Rules
- Do not keep two active implementations of the same rule without explicit reason.
- Do not remove legacy logic until replacement path is validated.
- Do not ship consolidation work without tests.
- Do not default to deprecation when hard removal is safe and validated.
