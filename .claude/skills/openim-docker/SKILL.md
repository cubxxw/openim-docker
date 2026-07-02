```markdown
# openim-docker Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you the core development conventions and operational workflows for the `openim-docker` repository. The project orchestrates OpenIM services using Docker Compose, with supporting configuration, deployment examples, CI/CD automation, and documentation. You'll learn how to update service definitions, manage deployment scenarios, maintain CI workflows, and keep documentation in sync, all while following the project's coding standards.

## Coding Conventions

### File Naming

- **Style:** kebab-case (all lowercase, words separated by hyphens)
- **Example:**  
  ```
  docker-compose.yaml
  full-openim-server-chat-web.yml
  ```

### Import Style

- **Relative imports** are used throughout the TypeScript codebase.
- **Example:**
  ```typescript
  import { startServer } from './server-utils';
  ```

### Export Style

- **Named exports** are preferred.
- **Example:**
  ```typescript
  export function startServer() { /* ... */ }
  export const DEFAULT_PORT = 8080;
  ```

### Commit Patterns

- **Prefixes:** `feat`, `fix` (e.g., `feat: add new service`)
- **Type:** Freeform messages, average 23 characters

## Workflows

### Update Docker Compose and Env

**Trigger:** When you need to update service definitions, environment variables, or deployment settings for OpenIM Docker  
**Command:** `/update-compose-env`

1. Edit `docker-compose.yaml` to change, add, or remove services or settings.
2. Edit `.env.example` to update, add, or remove environment variables.
3. Optionally update related example YAML files in the `example/` directory.
4. Commit all related changes together.

**Example:**
```yaml
# docker-compose.yaml
services:
  openim-server:
    image: openim/server:latest
    environment:
      - OPENIM_PORT=10000
```
```env
# .env.example
OPENIM_PORT=10000
```

---

### Multi-Example YAML Update

**Trigger:** When you need to propagate service/config changes across all deployment examples  
**Command:** `/update-examples`

1. Edit one or more files in `example/` (e.g., `basic-openim-server-dependency.yml`, `full-openim-server-chat-web.yml`).
2. Edit `docker-compose.yaml` and/or `.env.example` if needed.
3. Commit all changes together to keep deployment scenarios in sync.

**Example:**
```yaml
# example/full-openim-server-chat-web.yml
services:
  chat-web:
    image: openim/chat-web:latest
    ports:
      - "8080:80"
```

---

### CI Workflow Update

**Trigger:** When you want to improve or fix CI/CD pipelines  
**Command:** `/update-ci`

1. Edit one or more files in `.github/workflows/` (e.g., `openimci.yml`, `release.yml`).
2. Optionally update related documentation or configuration files.
3. Commit all workflow changes together.

**Example:**
```yaml
# .github/workflows/openimci.yml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Build Docker images
        run: docker-compose build
```

---

### Readme and Docs Update

**Trigger:** When you want to improve or update project documentation  
**Command:** `/update-docs`

1. Edit `README.md`, `README_zh-CN.md`, `FAQ-CN.md`, or other documentation files.
2. Optionally update related config or script files.
3. Commit documentation changes.

**Example:**
```markdown
# OpenIM Docker
This repository provides Docker Compose files for deploying OpenIM services.
```

## Testing Patterns

- **Framework:** Unknown (not explicitly detected)
- **Test File Pattern:** Files matching `*.test.*` (e.g., `server.test.ts`)
- **Example:**
  ```typescript
  // server.test.ts
  import { startServer } from './server-utils';

  test('server starts on correct port', () => {
    expect(startServer()).toBe(true);
  });
  ```

## Commands

| Command              | Purpose                                                        |
|----------------------|----------------------------------------------------------------|
| /update-compose-env  | Synchronize docker-compose.yaml and .env.example               |
| /update-examples     | Update all example deployment YAML files together              |
| /update-ci           | Update GitHub Actions workflow files in bulk                   |
| /update-docs         | Update README, FAQ, or other documentation files               |
```
