# Criteria commitment

The acceptance criteria for all ten issues were written before any delivery and are
deliberately absent from this repository. Their SHA-256 hashes are recorded here, in a
commit that predates every delivery branch, so that publishing the criteria afterwards
cannot be confused with writing them afterwards.

To check, once the criteria are published: `sha256sum <file>` and compare.

| SHA-256 | File |
|---|---|
| `777b6b5120593dfdc2ff5d1e105304eb3b77d63f350805450c9dfd4f1d13fabf` | `audit-trail.acceptance.test.js` |
| `f9959f0c5866c6130a1a531574653ab2dac463d8837547de363fe9f69b03ce24` | `capacity-window.acceptance.test.js` |
| `72f30eff781b620373b55a3ca80996904d992fc14d4668c6236b122900ce4e1c` | `clamp-window.acceptance.test.js` |
| `496bd794bfe967f541d3c7fb0fe7f3be880793267ffa0e73cbf5dafda26628a0` | `evidence-index.acceptance.test.js` |
| `f0367a1101163ffe5a9ad3ee00c85fdce97db286627c0483be2e4c96310b8e91` | `lease-ledger.acceptance.test.js` |
| `c3f01e80eac0c2226003fd6473e346d07bea4e4256e8c8c7ba833178ed700600` | `parse-duration.acceptance.test.js` |
| `181b972e51a577551f2ba9dd66780f4c4d76f59c8352bff76a7830fccc0ff154` | `retry-plan.acceptance.test.js` |
| `3cd4bef399bd4c379bcbfa156aed1094a23ba96064757a4d43ae500158480f3f` | `roster-assign.acceptance.test.js` |
| `d608a54c0b56c7d93629a81c94f88118aed2673569f9a52044a2dc3aafe9915f` | `slugify-role.acceptance.test.js` |
| `068ad3e4e8714719e8c06070b4ed0dc2ed85984bcf267f1b4402e13590764243` | `stage-graph.acceptance.test.js` |

Concatenated in the order above:
`b6fad17760acedb3c4261e25b92807feddc294d0eef0ad2e99431dcc3df2bccc`

Each file is a Node test module whose test names begin `AC1`, `AC2` and so on. Scoring
runs one criterion at a time against the pull request head and records it by name.
