# OwlMeans (local workspace)

OwlMeans builds full-stack web applications (a web interface, an API and a background worker) from
a plain-language description, and keeps developing them one user story at a time. This plugin runs
the OwlMeans MCP server on your computer, so the project OwlMeans generates is written into the
workspace Codex works in, where it can also be built and started. It adds a skill with the
working rules for that.

## Install

Add the marketplace, then install `owlmeans-local` from `/plugins` in Codex:

```sh
codex plugin marketplace add owlmeans/ai-packs
```

## What it runs, sends and stores

- **Runs:** `npx -y @owlmeans/viable-codex@0.1.21`, a local MCP server started by Codex.
- **Connects to:** the OwlMeans API at `https://api.owlmeans.com`. Project generation and story development run
  there and spend credits from your OwlMeans account; billing, plans and credit top-ups stay in the
  OwlMeans web app. The server writes the files the platform generates into your workspace.
- **Stores:** after you sign in, an access token in `~/.owlmeans` (or in the file the
  `OWLMEANS_CREDENTIALS` environment variable names). No other credential is read.
- **Asks first:** tools whose effect cannot be undone ask for confirmation.

## Sign in

The first tool call on a computer that is not signed in answers with a sign-in link and a code for
your browser. To sign in ahead of time, run this in a terminal:

```sh
npx -y @owlmeans/viable-codex@0.1.21 login
```

## While a run is active

OwlMeans writes into the workspace while it generates the project or implements a story. Do not
edit, move or delete workspace files until the run has finished.

If you also use the hosted OwlMeans plugin, enable only one of the two in a session: both offer the
same project tools.

## Links

- Documentation: https://owlmeans.com/docs/mcp
- Support: https://owlmeans.com/docs/help
- Privacy policy: https://owlmeans.com/legal/privacy
- Terms: https://owlmeans.com/legal/terms
- Website: https://owlmeans.com
