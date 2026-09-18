# CLAUDE.md

This file provides guidance to Claude Code when working with code in this
repository.

## What this repo is

This is `gomakeit-site`, the public source for `https://gomakeit.ai`. It
is a real, publicly reachable domain: anyone, including Meta's WhatsApp
compliance reviewers and search engines, can load it. Everything
committed here is public the moment it's pushed, permanently, in git
history as well as the working tree. There is no draft state once
something is committed.

## Hard rule: this repo serves a public domain and must never contain names

Never commit the name of any person, company, accelerator, or program.
Not a founder's name, not an outside company's name, not an accelerator
or investor's name, not a research-round codename, not anyone's name at
all. This applies to file content, commit messages, and this file itself.

The only names that belong here are the operator's own legal entity and
its public contact address, exactly as they appear in `/privacy` and
`/terms` today, and the vendor names the privacy policy is required to
disclose (the services it names as processing user data). If you're
about to type a name into anything in this repo and it isn't one of
those, stop and ask first rather than committing it.

This is enforced mechanically, not just by this instruction:
`.git/hooks/pre-commit` runs `gitleaks protect --staged` plus a
case-insensitive blocklist check against the staged diff, covering both
personal names and the organization/program names that have leaked into
this project before (see the hook script itself for the actual list, not
repeated here on purpose — repeating it would defeat the point). Don't
bypass it with `--no-verify`. A block is a signal to remove the flagged
content, not to force the commit through.

## Before committing

Before staging or modifying any file, read it back and ask: would this
read the same to a total stranger as it does to the team? If it names
someone, or something specific to how Make It operates internally that
isn't already meant to be public, it doesn't belong here.

Do not reference internal tracking numbers (issues, tickets, or similar)
anywhere in this repo, including this file and the README. They mean
nothing to a stranger reading a public legal page, and they're one more
thing that can accidentally imply information about people or
organizations that shouldn't be here.

## History

This repo replaces an earlier version of the same site whose git history
committed two outside organizations' names into a public file. That
version was deleted entirely rather than rewritten, and this repo starts
from a clean history with no carried-over commits. If you're tempted to
recover anything from an old clone, checkout, or reflog of the previous
repo, don't — that's exactly the content this rule exists to keep out.

## Structure

- `/index.html` — placeholder homepage, meant to be replaced by a fuller
  explainer page later.
- `/privacy/index.html`, `/terms/index.html` — the live privacy policy
  and terms of service.
- `CNAME` — GitHub Pages custom domain config for `gomakeit.ai`.
