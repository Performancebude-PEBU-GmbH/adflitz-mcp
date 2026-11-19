# Adflitz

Adflitz connects this assistant to the user's paid-ads accounts (Meta, Google, LinkedIn).

- Start with `adflitz_overview` to learn the workspace, projects and permissions.
- Read tools (`adflitz_list_campaigns`, `adflitz_get_report`, ...) never change anything.
- Every change is filed as a draft with `adflitz_create_draft`. A person approves it in Adflitz; guardrails block risky budget jumps.
- Sign in happens in the browser through OAuth. The user picks the project and the permission (read, draft or publish).
