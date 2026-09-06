# South African Education Resource Graph

A free, continuously updated directory of publicly accessible South
African educational resources — CAPS/NCS, IEB, Cambridge and other
curricula used in South Africa, from Grade R through university
preparation.

This project does not host or resell educational content. It indexes,
verifies, classifies and links to resources published by the Department
of Basic Education, the nine provincial education departments,
universities, publishers, OER providers, and credible independent
educators — and tells you, honestly, how authoritative and how usable
each one is.

## What's in this repository

```
sa-education-resource-graph/
├── MASTER-INSTRUCTIONS.md      # Claude Project operating instructions
├── WEEKLY-WORKFLOW.md          # the weekly update runbook
├── TAXONOMY-REFERENCE.md       # canonical grade/subject/curriculum labels
├── MONETIZATION.md             # ad network + compliance notes
├── agents/                     # role definitions for each phase of the pipeline
├── site-template/              # the HTML template the weekly build uses
├── data/                       # (create as needed) the resource dataset
├── reports/                    # (create as needed) coverage, broken links, gap reports
└── site/                       # the published GitHub Pages output
```

## How it's maintained

The dataset and the weekly HTML update are produced by a Claude Project
configured with the files in this repository (see
`MASTER-INSTRUCTIONS.md`). Each cycle: discover → classify → verify
authority and licence → deduplicate → score quality → check coverage
gaps → check link health → write descriptions → build the week's HTML →
audit → hand off. The output is a dated file
(`site/YYYY-MM-DD-update.html`) that gets committed and published via
GitHub Pages.

This is a human-in-the-loop process — nothing gets published without a
person reviewing the weekly hand-off, and anything with uncertain
copyright, licensing, or authenticity is routed to a review list instead
of the public site. See `MASTER-INSTRUCTIONS.md` §2 for the non-negotiable
rules the process follows every cycle.

## Publishing an update

1. Run the weekly cycle in the Claude Project.
2. Download the generated `YYYY-MM-DD-update.html`.
3. Add/commit it under `site/`, update `site/index.html` to link the
   latest edition if your structure uses a rolling index.
4. Push to the branch GitHub Pages serves from.

## Policy on resources

- **We link, we don't mirror.** Copyrighted material (textbooks, past
  papers, articles) is linked to its official source, never reproduced
  here.
- **Licence status defaults to closed.** A resource is only labelled
  "open" when we found an explicit open licence on the source.
- **Everything is labelled honestly by trust level (A–E)**, not filtered
  by it. An informal but useful teacher resource is included and marked
  as such, not hidden.
- **We don't fabricate.** Every resource, provider, URL, year, and licence
  claim is meant to trace back to something actually observed on the
  source page. If you find an error, please open an issue.

## Reporting a problem

Broken link, wrong classification, incorrect licence label, or a resource
that shouldn't be indexed (e.g. it turns out to be pirated) — please open
an issue with the resource's title/URL and what's wrong. We prioritise
copyright and safety corrections immediately.

## License

- Code and site templates in this repository: MIT — see `LICENSE`.
- Original curated metadata (descriptions, classifications, the resource
  graph itself): CC BY 4.0 — see `CONTENT-LICENSE.md`.
- Linked third-party resources remain the property of their original
  publishers under their own terms; this repository claims no rights over
  them. See `CONTENT-LICENSE.md` for full detail.
