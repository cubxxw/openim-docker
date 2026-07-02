---
name: multi-example-yaml-update
description: Workflow command scaffold for multi-example-yaml-update in openim-docker.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /multi-example-yaml-update

Use this workflow when working on **multi-example-yaml-update** in `openim-docker`.

## Goal

Update multiple example deployment YAML files (in example/) together, often alongside docker-compose.yaml and .env.example, to keep deployment scenarios in sync.

## Common Files

- `example/basic-openim-server-dependency.yml`
- `example/full-openim-server-and-chat.yml`
- `example/full-openim-server-chat-web-admin.yml`
- `example/full-openim-server-chat-web.yml`
- `example/only-openim-server.yml`
- `example/volume-all-server.yml`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit one or more files in example/ (e.g., basic-openim-server-dependency.yml, full-openim-server-chat-web.yml, etc.).
- Edit docker-compose.yaml and/or .env.example if needed.
- Commit all changes together.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.