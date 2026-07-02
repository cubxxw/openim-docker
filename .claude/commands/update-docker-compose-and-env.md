---
name: update-docker-compose-and-env
description: Workflow command scaffold for update-docker-compose-and-env in openim-docker.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /update-docker-compose-and-env

Use this workflow when working on **update-docker-compose-and-env** in `openim-docker`.

## Goal

Synchronize docker-compose.yaml and .env.example to update service configuration, environment variables, or deployment logic.

## Common Files

- `docker-compose.yaml`
- `.env.example`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit docker-compose.yaml to change/add/remove services or settings.
- Edit .env.example to update/add/remove environment variables.
- Optionally update related example YAML files in example/.
- Commit changes together.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.