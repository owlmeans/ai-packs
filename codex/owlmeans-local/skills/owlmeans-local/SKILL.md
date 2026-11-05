---
name: owlmeans-local
description: Working rules for building a full-stack web application with OwlMeans into the current local workspace. Use when the user asks to create an application with OwlMeans in this folder, to plan, implement or change its user stories, to follow a generation run, or to build and start the generated application on this computer.
---

# OwlMeans in this workspace

OwlMeans generates a full-stack web application (a web interface, an API and a background worker)
from a plain-language description, then keeps developing it one user story at a time. The model
work runs in the OwlMeans cloud; the OwlMeans tools of this plugin write the resulting project into
the current workspace, the folder this session works in, and can build and start it on this
computer.

## Working rules

- **The workspace receives the project.** Generation and story work write files into the current
  workspace. Start a new project in an empty folder, or in the folder of that same project, and tell
  the user which folder will receive it before you start.
- **Hands off while a run is active.** While OwlMeans generates the project or implements a story,
  it writes into the workspace. Neither you nor the user should edit, move or delete files in the
  workspace until the run has finished: tell the user so when a run starts, and check progress with
  `project_status` or `story_status`. Edits made during a run can be overwritten or make the run
  fail.
- **Credits.** Generating a project, implementing a story and the platform's other AI work spend
  credits from the user's OwlMeans account. A tool's description says when it spends credits. Start
  such work only when the user asked for it, and tell them what it will start.
- **Balance and billing.** When a tool reports that the balance does not cover the work, tell the
  user plainly. Plans, billing and credit top-ups are managed by the user in the OwlMeans web app;
  they are not available from this session.
- **Confirmation.** Tools whose effect cannot be undone (deleting a project or a story, stopping or
  replacing the production site, detaching a domain, reverting code) ask for confirmation. Explain
  what will happen and confirm only after the user agrees.
- **Repeated calls.** A tool that starts work repeats its effect when it is called again. While work
  is running, follow it with the status tools instead of starting it a second time.
- **Questions.** When the platform asks a question only the user can answer, put it to the user as it
  stands and send back their answer. Do not decide for them.
- **Sign-in.** The tools act for the OwlMeans account signed in on this computer. When a tool answers
  with a sign-in link and code, show them to the user, wait until they have signed in, then retry.
  The user can also sign in ahead of time from a terminal with `npx -y @owlmeans/viable-codex@0.1.21 login`.

## Typical flow

1. `list_projects`: see what exists before creating anything new.
2. `create_project`: pass the user's description; summarize the drafted specification for them.
3. `confirm_project`: once the user accepts the draft. This starts the build and the platform starts
   writing the project into the workspace.
4. `project_status`: follow the run until it has finished.
5. `list_stories`, `create_story`, `develop_story`, `story_status`: plan and implement the next
   features one user story at a time, each run finishing before the next starts.
6. `local_status`, `run_local`, `stop_local`: check this computer is ready, then build and start
   the application here.
