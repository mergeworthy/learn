# Reading a codebase

Before you change a line of code in an unfamiliar codebase, you need to orient yourself. This is the single most underrated skill in open source — and it's the difference between a PR that gets merged and a PR that gets a polite "this isn't quite how we do things here."

This guide is about the first 30 minutes you spend in a new repo.

## Read in a specific order

Don't open the source code first. Read these, roughly in order:

### 1. README.md

Sounds obvious, but most people skim it. Read it carefully. You're looking for:

- What the project actually does (often different from what you assumed from the name).
- The intended audience.
- How to install and run it.
- Any explicit "we do/don't do X" statements.

### 2. CONTRIBUTING.md

If it exists, this is where the maintainer has written down all the things they're tired of explaining. Read every line. Pay especially close attention to:

- Branch naming conventions.
- Commit message format.
- Any required pre-commit checks (linters, formatters).
- Whether they want issues opened before PRs.

### 3. The directory structure

Run `ls` (or look at the file tree on GitHub). Get a high-level sense of:

- Where the source code lives (`src/`, `lib/`, `app/`?).
- Where tests live (`tests/`, `__tests__/`, alongside source files?).
- Where docs live.
- What configuration files exist at the root (these tell you the build system, linter, formatter).

### 4. Package manifest

Open `package.json`, `pyproject.toml`, `Cargo.toml`, or whatever your language uses. Look at:

- The `scripts` section — these are the commands the maintainer expects you to run (test, build, lint).
- Major dependencies — these tell you the stack ("oh, they use React + tRPC + Prisma").

### 5. Recent commits

```bash
git log --oneline -20
```

This shows you what the project has been working on recently. Patterns to notice:

- Are commits small and focused, or large dumps?
- What's the commit message style? (You'll match this.)
- Who are the active maintainers?

### 6. One full file end to end

Pick a file related to the issue you're working on and read it top to bottom. Don't try to understand every line — just get a sense of:

- The naming conventions.
- The level of comments.
- The error handling style.
- How the file is structured (helpers at top? bottom? exports at the end?).

## Run it locally before you change anything

Before editing a single line, get the project running. Follow the README's install steps exactly. If something fails:

- **Don't immediately try to fix it.** First, search the issues tab — if 3 other people hit this, the maintainer knows.
- **Don't skip steps.** The README is usually right; missing prerequisites are usually the problem.

Once it's running, make a deliberately small, reversible change (add a `console.log`, change some text) and watch the change show up. This proves your dev loop is working before you stake real work on it.

<!-- TODO: contribution welcome — share a story about a time the dev environment setup was the hardest part of a PR -->

## Use the test suite as documentation

If the project has tests, they are often the clearest documentation of how things are supposed to work. When you're trying to understand what a function does:

1. Find the function.
2. Search the codebase for its name.
3. Read the test file that exercises it.

The test file will show you the inputs and expected outputs in a way that prose docs often don't.

## What "matching the style" actually means

When maintainers say "follow the existing style," they usually mean:

- Match the indentation, quote style, semicolons of the surrounding file.
- Match the naming patterns (camelCase vs snake_case, etc.).
- Match the comment density. If the file has zero comments, don't add three to your function.
- Match the abstraction level. If the file uses simple imperative loops, don't introduce a custom Observable pattern.

When in doubt: the existing code is right.

## The biggest mistake new contributors make

Trying to clean up unrelated code while they're at it. *"Oh, this function nearby is also messy, let me fix that too."*

Don't. The smaller and more focused your PR, the faster it gets reviewed and merged. Save the cleanup for a separate PR — and even then, only after your first one is merged.

## A 30-minute orientation checklist

When you start work on a new repo, spend 30 minutes on this before writing any code:

- [ ] Read README.md
- [ ] Read CONTRIBUTING.md (if it exists)
- [ ] Skim the directory structure
- [ ] Open the package manifest, note the scripts and major dependencies
- [ ] Look at the last 20 commits
- [ ] Read one source file end-to-end
- [ ] Get the project running locally
- [ ] Confirm the test suite passes before you change anything

If all eight take longer than 30 minutes, do them anyway. This is the work that prevents your PR from needing a rewrite.
