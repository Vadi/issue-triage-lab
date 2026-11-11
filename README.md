# Issue Triage Lab

A sandbox for one question: **how should a mixed team of engineers, QA and
business people file and triage GitHub issues?**

The convention under test:

- The **reporter** picks where they saw the problem, in plain words. No code
  terms, no priority, no prefixes in the title.
- **Triage** adds the technical labels: one `module:*` area, plus type, priority
  and state.
- A small workflow maps the reporter's dropdown answer to an area label, so the
  triage queue only contains the genuinely unclear cases.

## Try it

1. **File an issue** and pick an option from *Where did you see this?*
2. Watch the labels appear on the new issue within a few seconds.
3. Try **Somewhere else / not sure** — the issue should keep `needs-triage`
   instead of guessing.
4. Edit the dropdown answer and see the old `module:*` label get replaced.

## What is in here

| Path | What it does |
|---|---|
| `.github/ISSUE_TEMPLATE/bug.yml` | The form reporters use: plain dropdown + what happened |
| `.github/ISSUE_TEMPLATE/feature.yml` | Same, for requests |
| `.github/ISSUE_TEMPLATE/config.yml` | Disables blank issues so the dropdown is always present |
| `.github/labels.yml` | The label taxonomy, as code |
| `.github/workflows/label-sync.yml` | Applies `labels.yml` to the repo |
| `.github/workflows/issue-triage.yml` | Maps the dropdown answer to a `module:*` label |

## Labels

| Label | Meaning |
|---|---|
| `needs-triage` | Filed, area not yet set |
| `module:workspace` | The app families see and touch |
| `module:memory` | Where the child's record is kept |
| `module:brain` | Riya's background thinking |
| `module:workspace-api` | The link between the parts |
| `quality` | Riya said something wrong or off |
| `channels` / `website` | Real topics with no code in the app |
| `p0` / `p1` / `p2` | Priority |
| `needs-decision` / `needs-ba` | Waiting on someone |

Priority is deliberately **not** automated. A bot guessing `p0` is worse than no
label at all.

## Reset

Delete every issue in the repo and start again; the labels and workflows stay.
