# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer-alive | repo-facts block: last 5 default-branch commits and maintainer first-response sample | At least 2 of the last 5 default-branch commits are within 90 days of the capture date, or at least 1 owner/member/collaborator first response in the sample is within 30 days | required |
| repo-in-use | repo-facts block: last push to any branch, latest release, archived flag | The repository is not archived and either has a push within 180 days of capture or a release within 365 days of capture. Stars are adoption scale, not liveness: a low star count never fails this check on its own, and a repo with no published releases still passes on commit recency | required |
| scope-fits-newcomer | issue body and comment thread; apply the scope guidance in `references/evidence-guide.md` | Pass unless the issue hits one of these disqualifiers: it is explicitly an umbrella or tracking issue (a list of sub-items meant to be split into separate work); the desired end state is still undecided — the design is being debated with no maintainer having settled it, the work needs a product or design decision no maintainer has made, or it depends on a spec or asset that does not exist yet ("TBD"), and silence counts as undecided here, since an unanswered feature wish from a non-maintainer has been settled by nobody. Judge the end state, not the route to it: an issue whose desired result is clear fails nothing by listing candidate causes, hypotheses, or suggested approaches, which are implementation detail for whoever picks it up — that is a diagnosed bug, not an open question; a maintainer says the fix requires core-internal changes; or it is a pure usage/support question. Size the work asked for, not the polish of the writeup: a terse body, a bare checklist, or several related sub-items inside one area or file set is still one bounded contribution, especially when a maintainer or collaborator opened it or it carries a good-first-issue label. Enumerated work whose pieces are each specified — for example a docs task that names the pages to touch and the content each should carry — is bounded however many pieces it lists | required |
| unclaimed | repo-facts block: this issue's assignees and linked PRs; issue comment thread for claim comments and mentioned PRs | There are no assignees, no open linked or mentioned PRs, and no maintainer-confirmed active claim; student claim comments do not count where the scope's house rule says to ignore them | required |
| contribution-policy | repo-facts block: contribution policy, dedicated AI policy files, and templates | The repository does not ban AI-assisted contributions; stated disclosure, testing, or human-review conditions count as pass when they can be followed | required |
| no-abandoned-attempts | repo-facts block: this issue's linked PRs and their state; issue open date vs capture date; comment thread for mentioned PRs, claim-and-lapse cycles, and total comment count | Fail when the issue carries 2 or more closed, unmerged attempts (linked or mentioned in the thread) AND the thread shows the work never settled — a long thread (more than 20 comments) or repeated claim-then-lapse cycles. One abandoned attempt on a short, quiet thread is an old issue, not a trap, and passes | required |
| maintainer-response | repo-facts block: maintainer first-response sample | At least 1 of the 5 sampled recently updated issues has an owner/member/collaborator first response within 60 days | preferred |

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->


Accept only if every `required` check passes. Any required `fail` or
`unclear` produces `reject`; preferred checks never change the binary
verdict and only help rank issues that are accepted.
