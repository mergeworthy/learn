# Contributing

Welcome. If this is your first open source contribution, you're in the right place. This guide walks through every step assuming you've never done it before. If you already know parts of this, skim past them.

There is no such thing as a contribution that's "too small" here. Fixing a typo is a real contribution. Adding one link to a resource list is a real contribution. Adding your name to [contributors.md](contributors.md) is a real contribution.

## The full walkthrough

### 1. Find an issue to work on

Go to the [issues tab](https://github.com/mergeworthy/learn/issues) and look for ones labeled `good first issue`. Each issue has acceptance criteria (what "done" looks like) and an estimated time.

> **What this means:** An "issue" on GitHub is just a task someone has written down. Anyone can pick one up.

**Comment on the issue to claim it before you start working** — something like *"I'd like to take this on"* is enough. This prevents two people from doing the same work. If you don't see a response within a day or two, go ahead anyway.

### 2. Fork the repo

On the [repo's homepage](https://github.com/mergeworthy/learn), click the **Fork** button in the top-right.

> **What this means:** A "fork" is your own personal copy of the repo, hosted on your GitHub account. You can change anything in your fork without affecting the original.

<!-- TODO: screenshot of the Fork button -->

### 3. Clone your fork

Open a terminal and run (replace `your-username` with your actual GitHub username):

```bash
git clone https://github.com/your-username/learn.git
cd learn
```

> **What this means:** "Clone" downloads your fork onto your laptop so you can edit files locally.

### 4. Create a branch

```bash
git checkout -b add-resource/your-name
```

Branch names should follow this pattern:

- `add-resource/your-name` — adding to a resources list
- `fix-typo/short-description` — fixing a typo (e.g. `fix-typo/readme-contribution`)
- `add-guide/short-description` — adding or expanding a guide
- `update-contributors/your-name` — adding yourself to contributors.md

> **What this means:** A "branch" is a separate line of work. Creating one keeps your changes isolated and easy to review.

### 5. Make your change

Edit files in your text editor. Save when you're done.

For typo fixes: just fix the typo. Don't reformat surrounding text or rewrite paragraphs — keep the diff small and focused on what the issue asked for.

For resource additions: keep the format consistent with the surrounding entries (alphabetical order, one-line description after an em dash).

### 6. Commit your change

```bash
git add .
git commit -m "Fix typo: contribution in README"
```

Commit message format: a short imperative line that finishes the sentence *"This commit will..."*. Examples:

- `Fix typo: contribution in README`
- `Add Real Python to python/curated-links.md`
- `Add myself to contributors.md`

> **What this means:** A "commit" is a saved snapshot of your changes with a message explaining what changed.

<!-- TODO: screenshot of a clean commit message -->

### 7. Push your branch

```bash
git push origin add-resource/your-name
```

> **What this means:** "Push" uploads your local changes to your fork on GitHub.

### 8. Open a pull request

Go to your fork on GitHub. You'll see a banner suggesting you open a pull request from your branch — click **Compare & pull request**.

Fill in the PR template (it's already pre-filled with the right structure). Reference the issue number you're closing with `Closes #12` (or whatever the number is) so the issue closes automatically when the PR merges.

> **What this means:** A "pull request" (PR) is a proposal: *"Here's a change I'd like you to merge into the main repo."* Maintainers review it, may suggest changes, and then merge it.

### 9. Respond to review

A maintainer will review your PR. Common things you might hear:

- *"Can you also do X?"* — make the change, commit, push to the same branch. The PR updates automatically.
- *"This looks good, merging."* — you're done. Celebrate.
- *"Could you adjust this to match the style of the surrounding code?"* — totally normal feedback, not a rejection.

Reviews are not personal. They are how every PR — including ones from senior engineers — gets better.

### 10. Merge

Once a maintainer merges your PR, your contribution is officially part of the project. Your username appears in the contributors graph. Your commit shows up in `git log`. You've done it.

Now go add yourself to [contributors.md](contributors.md) if you haven't already.

## Stuck is normal

Every developer who has ever opened a PR has, at some point, been stuck. Specifically stuck on:

- *"Git is doing something weird and I don't understand"* — extremely common. Search for the exact error message; the answer is almost always on Stack Overflow.
- *"I think I broke my fork"* — you almost certainly haven't. Worst case, delete the fork on GitHub and re-fork. Nothing is permanent until it's merged into the main repo.
- *"I don't know if my change is good enough to submit"* — submit it anyway. The worst that happens is someone suggests an improvement.

If you're stuck for more than 30 minutes:

1. **Comment on the issue** describing what you tried and where you got stuck. Be specific (paste the error, paste the command). Maintainers and other contributors are happy to help.
2. **Don't delete your work.** Even broken progress is useful — share it.

## PR conventions summary

| Thing | Convention |
|---|---|
| Branch name | `add-resource/your-name`, `fix-typo/short-description`, etc. |
| Commit message | Imperative, finishes "This commit will..." |
| PR title | Same style as commit message |
| PR body | Use the template — fill in what the PR does and check the boxes |
| Linked issue | Add `Closes #N` so the issue auto-closes on merge |

## What we'll never do

- Reject a PR for being "too small."
- Reject a PR without explaining why.
- Make you feel bad for asking a basic question.

Welcome.
