# provider-phrases

SSOT for the fleet's **mandatory per-provider prompt phrases** —
the prefix/suffix/profile sets inserted into prompts by the JIT
phrase layer between prompt construction and model dispatch
(owner order, 2026-10-31).

- Data: `phrases.json` (`provider-phrases/v1`), keyed by provider,
  with `match` substrings for model routes, `prefixes`, `suffixes`,
  and named `profiles`.
- Consumption: `timerloggedout-spec/termux-monorepo` pins this
  repo as the `ops/phrases` git submodule; the DoE lab runner
  (`scripts/doe/phrase_layer.py` there) composes the selected
  phrases into the dispatched system prompt and covers them with
  the prompt hash — phrased and unphrased runs are different
  configured instances and never pool.
- Amendments: owner appends/amends sets per provider here;
  consumers bump the submodule pin by PR. Placement, selection,
  timing and character-substitution form are experimental
  variables under the DoE (see termux-monorepo
  `docs/ops/DOE-FAMILY.md`).
