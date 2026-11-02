# Midfleet delivery benchmark — blind condition

Ten software issues, delivered twice: once by a single agent working alone, once by a
governed team of agents coordinated by [Midfleet](https://midfleet.ai). Same issues,
same rules, same model. The question is not whether an agent can write the code. It is
whether the work gets **finished** — and whether the report at the end is true.

This repository is the **blind** condition. Its companion,
[midfleet-delivery-benchmark](https://github.com/ahmashadani/midfleet-delivery-benchmark),
is the **open** condition, where the acceptance criteria are committed in the
repository and either arm can run them before claiming to be done.

## Why two conditions

In the open condition both arms scored 87 of 87 criteria. That result is real, but it
answers a narrower question than it appears to. Every agent read the criteria file and
ran it before opening its pull request, so the arms were measured on *can you iterate
until a visible check goes green* — a thing agents are reliably good at. The failure
this benchmark exists to detect, a confident "all criteria met" over work that does
not meet them, cannot occur when the agent can simply look.

So the criteria are withheld here. They were written first, hashed, and the hashes
committed to this repository before a single line was delivered — see
[CRITERIA-COMMITMENT.md](CRITERIA-COMMITMENT.md). The criteria themselves are
published after the runs finish, and anyone can check them against the recorded
hashes.

## The rules

Both arms get the same thing: an issue containing a complete written specification, an
empty `src/`, and `npm run verify`, which runs only the delivery's own tests. There is
no acceptance suite to find. Scoring happens afterwards, off this repository, by
running each criterion against the pull request head.

The boundaries both arms work inside are in [AGENTS.md](AGENTS.md).

## The issues

| # | Slug | Tier | Criteria |
|---|---|---|---|
| [#1](https://github.com/ahmashadani/midfleet-delivery-benchmark-blind/issues/1) | `clamp-window` | easy | 5 |
| [#2](https://github.com/ahmashadani/midfleet-delivery-benchmark-blind/issues/2) | `slugify-role` | easy | 5 |
| [#3](https://github.com/ahmashadani/midfleet-delivery-benchmark-blind/issues/3) | `parse-duration` | easy | 5 |
| [#4](https://github.com/ahmashadani/midfleet-delivery-benchmark-blind/issues/4) | `retry-plan` | medium | 7 |
| [#5](https://github.com/ahmashadani/midfleet-delivery-benchmark-blind/issues/5) | `evidence-index` | medium | 7 |
| [#6](https://github.com/ahmashadani/midfleet-delivery-benchmark-blind/issues/6) | `capacity-window` | medium | 7 |
| [#7](https://github.com/ahmashadani/midfleet-delivery-benchmark-blind/issues/7) | `lease-ledger` | long | 14 |
| [#8](https://github.com/ahmashadani/midfleet-delivery-benchmark-blind/issues/8) | `stage-graph` | long | 13 |
| [#9](https://github.com/ahmashadani/midfleet-delivery-benchmark-blind/issues/9) | `audit-trail` | long | 12 |
| [#10](https://github.com/ahmashadani/midfleet-delivery-benchmark-blind/issues/10) | `roster-assign` | long | 12 |

87 criteria in total. The easy tier is near-mechanical and little divergence is
expected. The long tier is where an implementation can be substantially right and
still unfinished — invariants that span several operations, assignment problems where
the obvious approach strands a later step, a hash chain that has to survive redaction
and still detect tampering.

## Results

Published in `results/` once both arms have run, together with the criteria, the
per-criterion scores, and the cost and wall-clock time of each arm.
