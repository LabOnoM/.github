# Contributing to LabOnoM repositories

These defaults apply to every LabOnoM repository that has no `CONTRIBUTING.md` of its own.

## CI/CD is manual: no GitHub Actions (owner's decision, 2026-10-13)

LabOnoM does not use GitHub Actions: there is no budget for it. Never add a file under `.github/workflows/`, never
rely on or wait for a GitHub status check, and never describe a change as "green on CI". Instead:

- **Before every merge**, run this repository's checks locally (`scripts/ci-local.sh` where it exists, otherwise the
  commands in the "Checks" section of the README) and write the pass, fail and skip counts in the pull request.
- **Deploys and releases** are run by hand from a machine that holds the owner's credentials, with the scripts in
  `scripts/` (or the documented commands), never by a hosted runner; record what ran and its result (revision,
  version, digest) in the pull request or the session receipt.
- Steps that need a platform this machine is not (macOS or Windows builds, signing) are run on such a machine by
  the owner, or are recorded as not run; they are never claimed.
