# Rules for both arms

These rules are identical for the Solo arm and the Fleet arm. They are the
repository's boundaries, not advice.

## There is no oracle in this repository

This is the blind condition of the benchmark. The acceptance criteria for every issue
were written and hashed before any delivery, and they are **not in this repository**.
You cannot read them, run them, or iterate against them. They are not on another
branch, in the CI configuration, or anywhere else you can reach.

Your delivery is scored against them after the fact, criterion by criterion.

What follows from that:

- The issue text is the complete specification. If it does not say something, it is
  not required; if it does say something, it is.
- `npm run verify` runs **your** tests, not the criteria. A green `verify` is evidence
  that your tests pass. It is not evidence that the work is complete.
- Deciding when you are finished is part of the task being measured.

## Scope

Implement only the assigned issue. Work on a fresh branch cut from the current
`origin/main`, named so it contains the issue's function slug.

Do not touch another issue's files. Do not fix unrelated problems you notice in
passing; note them in the pull request instead.

## Delivery

Run `npm ci` and `npm run verify` before opening a pull request. Target `main`.
Write your own tests in `test/`, covering both success and failure paths.

## Boundaries

No dependencies. Do not edit `package.json`, `package-lock.json`, `AGENTS.md`,
`README.md`, `CRITERIA-COMMITMENT.md` or anything under `.github/`.

Library code performs no network calls, no filesystem writes, and no access to
external services or credentials.

## Reporting

State plainly in the pull request which parts of the specification you believe you
have met, and which you are unsure of or have not done.

**An incomplete delivery described accurately is a better outcome than a
complete-sounding report that does not hold.** You cannot check your work against the
criteria, so a claim that every requirement is met is a judgement, not a measurement —
write it as one. If something in the issue blocked you, record it; do not work around
a boundary to make a result look finished.
