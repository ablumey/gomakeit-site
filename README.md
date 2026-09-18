# gomakeit-site

The public site for [gomakeit.ai](https://gomakeit.ai), hosted on GitHub
Pages. Currently holds the privacy policy and terms of service
(`/privacy`, `/terms`) plus a placeholder homepage; a fuller explainer
page is meant to replace `index.html` later, in this same repo.

This repo replaces an earlier version of the same site that briefly
committed the names of two outside organizations into a public file.
That version was deleted entirely, not history-rewritten, and this repo
started over with clean history. See `CLAUDE.md` for the rule that's
meant to stop that from happening again.

Deploy: push to `main`; GitHub Pages serves the repo root directly
(source = `main` branch, root). Custom domain `gomakeit.ai` is set via
the `CNAME` file plus DNS records at the registrar.
