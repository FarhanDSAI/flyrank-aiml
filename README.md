# FlyRank Search Intelligence Capstone

**Lane:** Ranking Signal Analysis
**Question:** Which safe content/search signals are associated with visibility,
clicks, engagement, or movement — and how strong/robust is that association
once confounders (query segment, page age/volume tier, site section) are
controlled for?

## Repo structure

- `work/` — every weekly assignment notebook, plus the capstone notebook.
  Number them in order (01_..., 02_..., etc.) so the analysis reads
  chronologically.
- `submission/paper_url.txt` — **mandatory**. Exactly one line: the direct
  URL of the deployed paper. This is how the paper gets found — keep it
  up to date the moment you deploy or redeploy.
- `paper/` (optional, if deploying via GitHub Pages from this repo) — the
  static site source for the deployed research paper.

## Paper section checklist

Matches the required capstone sections. Check off as drafted:

- [ ] Title + Abstract (5 sentences: question → method → result)
- [ ] Introduction / Problem statement (what decision this supports)
- [ ] Data (release, tables, date windows, exclusions — public-safe)
- [ ] Methodology (assumptions, features, label/outcome definition,
      baseline, validation design — segment- or time-aware split,
      leakage checks)
- [ ] Results (model/association vs baseline, same split, with charts)
- [ ] Limitations & honest framing (observed / directional /
      decision-support language — no causal claims)
- [ ] Ranked recommendations (action playbook)
- [ ] Reproducibility (links to notebooks + repo)
- [ ] Acknowledgments & data credit — "Built on the FlyRank ML Internship
      dataset" linking to https://flyrank.ai

## Public rule (hard constraint)

No client names, domains, URLs, private queries, credentials, raw exports,
or claims that prove Google's algorithm or causal refresh impact. Anything
in `work/` or the deployed paper must be public-safe.

## Leakage checklist for this lane

Before treating any signal as "associated with" the outcome, confirm:

- [ ] Signal is measured from a time window at or before the outcome
      window (no future-dated signals explaining past outcomes)
- [ ] Signal is not partially derived from the outcome itself
      (e.g., don't use total clicks as a "signal" to explain CTR)
- [ ] Association is checked within query/topic segments, not just
      site-wide, to avoid confounding by intent or competitiveness
- [ ] Controlled for page age / query volume tier
- [ ] Controlled for site section / template
- [ ] Reported as partial correlation or regression coefficient with
      controls — not a raw pairwise correlation
- [ ] Out-of-sample check on a held-out time window or query segment,
      not just in-sample eyeballing
- [ ] Compared against a naive baseline (e.g., traffic-only ranking) to
      confirm added signals actually explain more
