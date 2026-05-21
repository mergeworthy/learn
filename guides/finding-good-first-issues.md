# Finding good first issues

Most "first PR" advice tells you to search GitHub for `label:"good first issue"` and pick one. That's the right starting point — but the label alone doesn't tell you whether the issue is *actually* a good fit, or whether the repo around it is a place you'll have a good experience.

This guide is about the second part: how to read the surrounding signals.

## How to search effectively

GitHub's issue search supports filters. The most useful starting query:

```
label:"good first issue" is:open is:issue language:javascript no:assignee
```

Swap `javascript` for whatever language you want. The `no:assignee` filter is important — it hides issues someone is already working on.

You can also combine labels:

```
label:"good first issue" label:"help wanted" is:open
```

Search this from [github.com/issues](https://github.com/issues) (after logging in) or use the [advanced search](https://github.com/search/advanced).

## What makes an issue actually beginner-friendly

A real beginner-friendly issue has most of these:

- **A clear description** of what needs to change. Not "fix the parser" — something more like "the parser crashes on input `X`; we'd like it to return `Y`."
- **Acceptance criteria** — a list of things that must be true for the issue to be considered done.
- **A pointer to the relevant file or function.** The maintainer has done the "where in the codebase" work for you.
- **Recent activity from the maintainer** in the comments — they responded to questions, they're around.
- **A scope that fits in 1–3 hours.** Beginner-friendly should mean small, not just "labeled beginner-friendly."

## Red flags in a repo

You can save yourself a lot of frustration by checking these *before* you start working on an issue:

### Silent maintainers

Look at the repo's recent PRs and issues. If maintainers haven't responded to anything in 3+ months, your PR will likely sit too. Check:

- The "Issues" tab — are recent issues getting responses?
- The "Pull requests" tab — are PRs being reviewed and merged, or are there 50+ open ones with no comments?
- The repo's [Insights → Pulse](https://docs.github.com/en/repositories/viewing-activity-and-data-for-your-repository/viewing-a-summary-of-repository-activity) page for recent activity.

If the most recent merged PR is from a year ago, move on.

### Stale issues

An issue labeled `good first issue` that's been open for 18 months with no activity is a warning sign. Either:

- It's not actually beginner-friendly (multiple people tried and bounced), or
- The maintainer doesn't actually want it solved (sometimes labels get auto-applied).

Issues with recent comments are safer.

### No CONTRIBUTING file

If the repo has no `CONTRIBUTING.md`, no PR template, and no obvious signs anyone has thought about new contributors, you're on your own. That's fine when you're more experienced — for a first PR, prefer repos that have done some of this work.

### Maintainer responsivness

A rough heuristic: look at the last 5 closed PRs. How long between PR open and first maintainer comment? Under a week is great. Over a month means you're going to be waiting.

## A safer search workflow

1. Start with the label filter above for your language.
2. Click into 5–10 candidate issues.
3. For each, open the repo's main page in another tab. Check: last commit date, last merged PR date, presence of CONTRIBUTING.md.
4. Pick the issue from the repo with the freshest activity.
5. Comment on the issue to claim it before you start coding.

That last step matters more than people realize. A 2-line comment — *"Hi! I'd like to take this on, planning to start this weekend"* — gives the maintainer a chance to flag if the issue has changed, and prevents you from racing another contributor.

## Where to find curated lists

Some sites pre-filter for beginner-friendliness:

- [goodfirstissue.dev](https://goodfirstissue.dev/)
- [up-for-grabs.net](https://up-for-grabs.net/)
- [firsttimersonly.com](https://firsttimersonly.com/)

These lists are useful but not magic — apply the same red-flag checks above before committing time to an issue.