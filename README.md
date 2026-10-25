# handover-ci-demo

A small, self-contained CI demo for onboarding. Nothing here is production code —
it exists so a new teammate can safely poke at a real repository, a real
GitHub Actions workflow, branches, and issues without touching anything else.

## What's in here

| Item | Where | What it is |
| --- | --- | --- |
| Smoke workflow | `.github/workflows/smoke.yml` | Runs on every push and on manual dispatch; a single job whose only step echoes `HANDOVER-SMOKE-OK` |
| Sandbox branch | `teammate-sandbox` | Scratch space branched off `main`. Experiment freely here. |
| Handover checklist | Issue #1 | Parent issue tracking the onboarding checklist |
| Verify smoke workflow | Issue #2 | Sub-issue: confirm the workflow still runs green |
| Check code scanning alerts | Issue #3 | Sub-issue: review the Security tab for open alerts |

## Exercises to try

1. **Read the workflow.** Open `.github/workflows/smoke.yml` and find the line
   that prints the marker. Note the two triggers: `push` and `workflow_dispatch`.
2. **Run it manually.** Go to the *Actions* tab, select **Smoke test**, and use
   **Run workflow**. Watch the job finish green.
3. **Inspect the log.** Expand the job's log and confirm you can see
   `HANDOVER-SMOKE-OK` in the output. (Note: the logs of the very first run
   and its repeat were deliberately deleted as part of this exercise — that's
   why they're not there. New runs keep their logs.)
4. **Use the sandbox branch.** Check out `teammate-sandbox`, push a trivial
   commit, and see the workflow trigger automatically from the `push` event.
5. **Break it on purpose.** In the sandbox, change the echo step so the job
   fails, and read the failure log to see what a red run looks like.

## Notes

- Default branch: `main`
- Repository: `mcpmark-eval-liuhezi/handover-ci-demo`
- If you get stuck, the issue list is the map of what's left to verify.
