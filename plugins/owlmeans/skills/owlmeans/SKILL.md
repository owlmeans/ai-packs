---
name: owlmeans
description: Build, develop and publish full-stack web applications on the OwlMeans platform with the OwlMeans tools. Use when the user wants to start an application from a description, review or confirm its specification, plan or implement user stories, follow a build, or check or manage a project's preview, production site, custom domain, application users or GitHub repository on OwlMeans.
---

# OwlMeans

OwlMeans generates a full-stack web application (a web interface, an API and a background worker)
from a plain-language description, then keeps developing it one user story at a time. The OwlMeans
tools work on the user's OwlMeans account: their projects, the user stories planned for each
project, the cloud preview, and the published production site. Everything runs in the OwlMeans
cloud; nothing is built or started on this computer.

## Before you act

- **Credits.** Generating a project, implementing a story and the platform's other AI work spend
  credits from the user's OwlMeans account. A tool's description says when it spends credits. Start
  such work only when the user asked for it, and tell them what it will start.
- **Balance and billing.** When a tool reports that the balance does not cover the work, tell the
  user plainly. Plans, billing and credit top-ups are managed by the user in the OwlMeans web app;
  they are not available from this conversation.
- **Confirmation.** Tools whose effect cannot be undone (deleting a project or a story, stopping or
  replacing the production site, detaching a domain, reverting code) ask for confirmation. Explain
  what will happen and confirm only after the user agrees in this conversation.
- **Repeated calls.** A tool that starts work repeats its effect when it is called again. While work
  is running, follow it with the status tools instead of starting it a second time.
- **Questions.** When the platform asks a question only the user can answer, put it to the user as it
  stands and send back their answer. Do not decide for them.

## Typical flow

1. `list_projects`: see what exists before creating anything new.
2. `create_project`: pass the user's description. The platform drafts a specification; summarize
   it for the user.
3. `confirm_project`: once the user accepts the draft, or after their edits. This starts the
   build, which runs in the cloud for several minutes.
4. `project_status`: follow the build and report where the project stands.
5. `list_stories`, `create_story`, `develop_story`, `story_status`: plan the next features as user
   stories and implement them one at a time.
6. `production_status`: check the published site before changing it with the production tools.

Report results in the user's terms: what changed in their application, what is running, what needs
their decision.
