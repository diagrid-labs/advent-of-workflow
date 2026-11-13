# SETUP-TEST: deferred verification for Task 2

**Status: NOT YET RUN.** This is the deferred clean-machine test for Task 2, Step 6. It must be run by a person who is not Marc, from scratch, on both a clean Windows machine and a clean macOS machine, following only the README. Record the result per step. Any step that needs knowledge not in the README is a README bug: fix the README, then rerun.

Remove this file from the public repo once both runs pass.

Machine: [ ] Windows  [ ] macOS     Tester: ______     Date: ______

| # | Do this | Expected result | Pass |
|---|---------|-----------------|------|
| 1 | Open the repo on GitHub and click Fork. | A fork exists under your account. | |
| 2 | Clone your fork and read README.md top to bottom without other sources. | Every prerequisite is listed once, in order, and nothing refers to something undefined. | |
| 3 | Follow "Dapr 1.17 or newer, and a container runtime": install and start Docker Desktop or Podman, install the Dapr CLI, run `dapr init`, then `dapr --version`. | `dapr init` completes (it fails without a running container runtime). `dapr --version` shows CLI and runtime both at 1.17 or higher. | |
| 4 | Install a toolchain for one language named in the README. | The language's own version command works. | |
| 5 | Run the Dev Dashboard install command for your OS exactly as written. | Install finishes without error and states the install location. | |
| 6 | Open a new terminal and run `diagrid-dev-dashboard --version`. | Reports a version. If "command not found", the README's PATH note was enough to fix it. | |
| 7 | Run `diagrid-dev-dashboard`. | Browser opens at http://localhost:9090 with no login or account prompt. | |
| 8 | With the dashboard open, follow the README "Smoke test" for one language, using the dapr/quickstarts `fundamentals` quickstart (Python: `tutorials/workflow/python/fundamentals`, run `uv run dapr run -f .`; or .NET: `tutorials/workflow/csharp/fundamentals`, run `dapr run -f .`). | The app (app id `basic`) appears in the dashboard within one refresh cycle. | |
| 9 | Start a run with `curl -i --request POST http://localhost:5254/start/One`. In the dashboard open Workflows, then the run. | The run detail page shows the run with its activities and statuses. | |
| 10 | Screenshot that run detail page. | The screenshot clearly shows the run and matches what the README describes as evidence. | |
| 11 | Reread README section 6 (free Diagrid account). | You can say in one sentence the difference between the Dapr Dev Dashboard (local, no account) and Diagrid (free account, optional bonus steps only). | |
| 12 | Reread README section 5 (`dapr-skills`) and Languages. | It is clear the plugin is optional, why, and which languages it covers; you could proceed without it. | |
| 13 | Click every link in README.md and `.github/challenge-template.md`, and open the repo's "New issue" page. | No link 404s. The New issue page offers no issue template, only the contact links from `.github/ISSUE_TEMPLATE/config.yml`. Links to repos not yet public are listed in Notes. | |
| 14 | **LAUNCH BLOCKER:** open CODE_OF_CONDUCT.md and search for `REPORTING CONTACT TO BE SET BEFORE LAUNCH`. | The text is gone and a real, monitored reporting address is in its place. **The repo must NOT go public while this placeholder remains.** | |
| 15 | **LAUNCH BLOCKER:** search README.md for "Maintainer note". | No match. Any maintainer note is deleted. **The repo must NOT go public while one remains.** | |
| 16 | **LAUNCH BLOCKER:** check the repo root for SETUP-TEST.md. | The file is removed. **The repo must NOT go public while it is present.** | |
| 17 | Note every place you hesitated, guessed or searched elsewhere. | Zero undocumented steps. List each under Notes. | |

## Notes

(Tester records trip points, OS-specific issues and README fixes here.)

## Pre-launch re-test

The day before launch (30 November 2026), rerun steps 5 to 10 against the current Dev Dashboard release and confirm the install still works and the Workflows view still matches what the challenges describe.
