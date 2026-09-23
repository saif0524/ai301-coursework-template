# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/69

**Verdict output**

[Your skill's live-mode output for this issue, pasted verbatim and ending with the
fenced JSON verdict block. A summary does not satisfy this field.]

**The verdict must record `accept` for this issue.** Choose an issue your own skill
accepts. If your skill rejects every candidate you try, that is a signal about your
rubric rather than about the issues: revise it and re-run — retries are unlimited and a
partial re-run costs about $0.20 — or run the skill on different candidates. Output
recording `reject` for the issue you chose earns no credit for this field.

```
Live-mode run of issue-select on that URL — scope confirmed (issue is in the Path Review repo named in scope.md), house rule applied, evidence gathered per references/evidence-guide.md against a 2026-09-23 capture:

Candidate: https://github.com/codepath/pathreview-ai301-fa26-s1/issues/69
"Output parser crashes on a top-level JSON array fallback" — labels: bug, good first issue, rag, tier-1

- maintainer-alive — pass. Last 5 default-branch commits are 2026-09-16 (x3, Aburke225) and
  2026-08-24 (x2, Aburke225); at least 2 fall within 90 days of the 2026-09-23 capture.
- repo-in-use — pass. "archived": false, and last push to any branch
2026-09-16T21:48:27Z,
  7 days before capture, inside the 180-day window. No releases published and
only 2 stars;
  per the check, stars are adoption scale and never fail it alone, and a repo
with no
  releases still passes on commit recency.
- scope-fits-newcomer — pdy names the defect ("calls .items() on
  the parsed value and raobject has no attribute'items'"), the
  desired end state ("The array responses"), the two files
  (rag/generator/output_ptput_parser.py) and thecleanup ("remove
  the marker as part of tORATOR, labelled good first issue,
  estimated 2-4 hours. Nod design, no core-internals warning.
- unclaimed — pass. "Assithe repo's only PR, #74,closes #60).
  Both thread comments ariation NONE), a classmate's claim, which
  scope.md's Path Review d: "other students' claimcomments ... do
  not block an issue". No
- contribution-policy — pass. No CONTRIBUTING.md at root or in .github/, no
AI_POLICY.md or
  AGENTS.md, and .github/PULL_REQUEST_TEMPLATE.md carries no AI-use restriction.
Silence
  passes; nothing bans AI-assisted contribution.
- no-abandoned-attempts —d PRs, 2 comments total(threshold is
  more than 20), opened 2apture. Zero closedunmerged attempts.
- maintainer-response (prst recently updated items(#72, #63, #62,
  #70, and PR #74), no thLABORATOR first response:every comment
  is from a NONE-associatt does not change theverdict; it is a
  reason to expect slow r.

All required checks pass
{
  "item": "https://github01-fa26-s1/issues/69",
  "checks": [                                                                       {"name": "maintainer-idence": "Last 5default-branch commits dated 2026-09-16 (x3) and 2026-08-24 (x2), all within 90 days of the 2026-09-23 ca
    {"name": "repo-in-use", "grade": "pass", "evidence": "\"archived\": false;  last push 2026-09-16T21:4, inside the 180-daywindow."},                                                                          {"name": "scope-fits-"evidence": "Names thedefect, the desired end state (\"The fallback path should handle array          responses\"), two files, ; COLLABORATOR-opened, good first issue."},                                                                     {"name": "unclaimed",: "\"Assignees: None\", nolinked PR; both comments are NONE-association classmate claims, which scope.md'shouse rule says do not bl
    {"name": "contribution-policy", "grade": "pass", "evidence": "No            CONTRIBUTING.md, AI_POLICte states no AI restriction — silence passes."},                                                                {"name": "no-abandone, "evidence": "No linked or mentioned PRs; 2 comments total, opened 13 days before capture — no closed      unmerged attempts."},
    {"name": "maintainer-response", "grade": "fail", "evidence": "None of the 5 most recently updated iteBORATOR first response; all commenters are NONE."}
  ],
  "verdict": "accept"
}

```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

15/20 → 18/20 → 18/20 → 19/20 → 18/20 → 20/20

Six full runs in order. The last, 20/20, is the one in the committed eval-run.txt, whose line 53 reads agreement: 20/20 scored items  (bar: 18/20: PASS).

**Issue analysis**

 issue-06 (Itqan-community/quran-apps-directory#298). Gold label: accept. My rubric's first run said reject; it says accept now.

The failing check was repo-in-use, whose original pass condition ended ...it has at least 100 stars. The bundle's repo line reads repo: Itqan-community/quran-apps-directory (37 stars, archived: no), so a required check failed on star count alone even though the same block shows last push to any branch: 2026-07-31 — five days before the 2026-08-05 capture — and five merge commits in the two weeks prior. The gold note is explicit that this is the wrong read: "bounded UI bug in a small but visibly active repo; no releases, commits carry liveness." I had taken a signal the evidence guide files under "Adoption scale" and promoted it to a liveness gate, so small-but-alive repos were indistinguishable from dead ones. Removing the star clause flipped it to accept.

**Check rationale**
repo-in-use, as currently written:
▎ | repo-in-use | repo-facts block: last push to any branch, latest release, archived flag | The repository is not archived and either has a push within 180 days of capture or a release within 365 days of capture. Stars are adoption scale, not liveness: a low star count never fails this check on its own, and a repo with no published releases still passes on commit recency | required |

Two things forced this form. The star floor had to go for the reason above. The disjunction between push and release had to be stated explicitly because of the same issue: its repo-facts line reads latest release: none published, so a rubric requiring a release would reject every young or unreleased project. The two clauses are or-joined so either one can carry the check, and the two trailing sentences exist because the first version's silence on those cases is what the grader filled in wrongly.
**Trade-offs**

It gives up the ability to reject a repo nobody uses. A repo pushed to last week with two users and two stars now passes, and I can show that it does: the live run above passes repo-in-use on the Path Review repo itself, whose API reports "stargazers_count": 2. I accept that miss, because within this eval set adoption never decides an item and staleness always does.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

Answer all three:

1. The issue's fit to your interests and to the time available.
   #69 is in rag/generator/output_parser.py — parsing LLM responses, the most AI-engineering-shaped issue on the board. The repo also has frontend/, api/ and agent/ directories which fulfills the criteria for fullstack dev. Estimated 2-4 hours, tier-1.
2. What the verdict identified correctly, and what you weighed that the rubric could
   not.
   that maintainer-response failure is real — staff file issues here but don't answer threads, so nobody will unblock you. And jacho15 has already posted a full reproduction on #69, two comments deep, four days ago.
3. The anticipated difficulty in claiming it.
#68 (BM25 empty-corpus guard, also rag/, one claimant) is an equivalent backup; it has no assignee and no linked PR either.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
