# Project Cleanup And Push

## Purpose
Use this skill to finalize a repository safely before release: audit changes, clean unrelated files, run validations, commit, push via SSH, and verify deployment health.

## Workflow
1. Assess repository state.
- Run `git status --short` and `git diff --stat`.
- Categorize changes as keep, discard, or investigate.

2. Validate before cleanup.
- Run targeted tests for touched modules.
- Stop and fix failures before commit.

3. Clean workspace.
- Remove unintended edits and temporary files.
- Keep only intentional, reviewed changes.

4. Commit and push.
- Use conventional commit format.
- Push with SSH remotes only.

5. Deploy and verify.
- Run `docker compose up -d --build`.
- Verify all services are healthy with `docker compose ps`.

## Completion Checklist
- Tests pass for changed scope.
- Workspace is clean after commit.
- Push succeeded via SSH.
- Deployment is healthy.
