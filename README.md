# Stinky Paker

AOSC CI System, which is stinky and helpful.

Usage
--------

This set of programs are written for GitHub Actions.  
We are already used to work with standard GitHub workflow, it's time to utilize GitHub Actions to automate this!

### Daily Routines

Paker checks for updates of specific packages. These packages have to be easy to maintain, which is suitable for automated scripts.

If any update is found, an paker survey PR will be filed.

> **Note**
> The PR must be filed with a Personal Access Token (PAT) in order to trigger the PR workflow.
> This means that PAT have to be present in the environment.

### PR workflow

If `use-ci` tag is present in a PR, Paker automatically launches Ciel to build the packages involved. Paker will post build result to the comment, and will update the checkmarks in the PR body.

Paker performs the follwoing sanity checks:

- Whether affected packages consistents with commits in this PR
- RELs are correctly bumped

### After PR merge

Paker launches Ciel to build the packages, for PRs with `use-ci` tag only.
