# GitHub Actions Lab

## Workflow 1: Dependent Jobs (dependent-jobs.yml)
**Purpose:** Demonstrates job dependencies using the `needs` keyword so jobs run in a strict order.  
**Execution order:** build → test → deploy

**Key concepts demonstrated:**
- `needs`: makes a job wait for another job to finish (example: test needs build, deploy needs test).
- `runs-on`: chooses the runner OS (used: ubuntu-latest).

## Workflow 2: Multi-Platform Testing (multi-platform.yml)
**Purpose:** Demonstrates running independent jobs in parallel on different operating systems.  
**Platforms:** Ubuntu, Windows, macOS

**Key concepts demonstrated:**
- `runs-on`: runs jobs on different operating systems (ubuntu-latest, windows-latest, macos-latest).
- Parallel execution: jobs run at the same time because there is **no `needs`** between them.
- `actions/checkout@v4`: checks out the repository code so the runner can access files.
- `env`: environment variables (not required in this lab, but can be used to store shared values for jobs/steps).

## Challenges & How I Resolved Them
- **Workflow did not trigger at first:** the branch name in the trigger did not match the repository default branch.  
  **Fix:** updated the workflow trigger branch to match the correct branch (master/main).
- **YAML indentation errors:** GitHub Actions failed because YAML is sensitive to spacing.  
  **Fix:** corrected indentation and re-committed the workflow files.
