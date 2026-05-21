# Your first PR checklist

Before you click "Create pull request," walk through this checklist. It catches the things that turn a clean merge into three rounds of review.

## Pre-flight: before committing

### The change itself

- [ ] **My change does only what the issue asked for.** No bonus refactors, no unrelated style fixes, no "while I'm here" cleanups.
- [ ] **I've read the issue's acceptance criteria** and my change satisfies all of it.
- [ ] **I haven't introduced any new dependencies** without checking with the maintainer first. If you needed a new package, comment on the issue before adding it.
- [ ] **I haven't deleted anything I don't understand.** If you removed code because "it looked unused," double-check it isn't called via a string lookup, dynamic import, or something the static analyzer missed.

### The surrounding code

- [ ] **My change matches the style of the file I edited.** Same indentation, same quote style, same comment density.
- [ ] **I haven't reformatted code I didn't otherwise change.** Even if the formatter does it automatically, configure it to only run on changed lines.
- [ ] **My new code doesn't introduce a pattern that doesn't exist elsewhere in the codebase.** If the repo doesn't use Promises and you're about to introduce one, ask first.

### Tests

- [ ] **The existing test suite still passes.** Run it locally, all the way through.
- [ ] **If I added new behavior, I added a test for it.** Even a simple one.
- [ ] **If I fixed a bug, I added a test that would have caught the bug.** This is the maintainer's most common ask — pre-empt it.

### Documentation

- [ ] **If my change is user-facing, I updated the relevant docs.** README, examples, JSDoc comments — wherever the behavior is described.
- [ ] **My commit messages are clear** and follow the project's convention.

## The PR itself

### PR title

- [ ] **Short and specific.** "Fix typo in README" is great. "Updates" is not.
- [ ] **No prefixes the maintainer doesn't use.** Don't add `[FEAT]` or `(WIP)` unless you've seen them in other PRs in the repo.
- [ ] **No emoji unless the project's existing PRs use them.**

### PR body

- [ ] **First line says what the PR does** in one sentence.
- [ ] **Second paragraph (if needed) says why** — what problem this solves, what issue it closes.
- [ ] **`Closes #N`** is included so the issue auto-closes when the PR merges.
- [ ] **I've filled in the project's PR template** if there is one. Don't delete sections — answer "N/A" if a section doesn't apply.
- [ ] **I haven't included anything irrelevant** (tangents, complaints, "PS" notes about other things you noticed).

### Mechanical checks

- [ ] **My branch is based on the latest `main`** (or whatever the default branch is).
- [ ] **I have no merge conflicts** showing on the PR page.
- [ ] **CI checks have passed** (or I'm waiting for them — don't @-mention anyone until they're green).
- [ ] **I haven't included any files I didn't mean to** (`.DS_Store`, IDE config, log files, secrets — especially secrets).

## After opening the PR

- [ ] **I commented on the linked issue** to note the PR is up.
- [ ] **I'm watching the PR for review notifications** — not refreshing every hour, but I'll respond within a day or two if asked.
- [ ] **I've resisted the urge to @-mention the maintainer** unless it's been more than two weeks with no response.

<!-- TODO: contribution welcome — what's something you wish you'd checked before your first PR? -->

## When something fails after you push

CI is red, or the maintainer asked for changes. This is normal and not a setback.

1. Make the fix locally.
2. Commit it (don't squash old commits — that comes later).
3. `git push origin your-branch-name` — the PR updates automatically.
4. If the maintainer left a review comment, reply to it once you've addressed it.

## What "good" looks like

A PR that gets merged on the first review usually has:

- A diff under 100 lines.
- A clear, focused commit message.
- Tests that match the change.
- Zero unrelated edits.
- A response from the contributor within a day if the maintainer asks something.

You don't have to hit all of these your first time. But this is the bar to aim for.