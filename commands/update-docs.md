---
description: Sync documentation with the codebase, generating from source-of-truth files.
---

# Update Docs Command

Sync documentation with codebase.

## Execution

1. **Identify Sources of Truth**:
   - `package.json` scripts → Commands reference
   - `.env.example` → Environment docs
   - `openapi.yaml` → API reference
   - Source code exports → Public API docs
   - `Dockerfile` / `docker-compose.yml` → Infrastructure docs

2. **Generate Script Reference** from package.json/Makefile/Cargo.toml

3. **Generate Environment Documentation** from `.env.example`:
   - Categorize as required vs optional
   - Document format and valid values

4. **Update Contributing Guide** (`docs/CONTRIBUTING.md`):
   - Dev environment setup
   - Available scripts
   - Testing procedures
   - Code style
   - PR checklist

5. **Update Runbook** (`docs/RUNBOOK.md`):
   - Deployment procedures
   - Health checks
   - Common issues
   - Rollback procedures

6. **Staleness Check** - Flag docs not modified in 90+ days

## Rules

- Single source of truth: Generate from code, never manually edit generated sections
- Preserve manual sections: Only update generated sections
- Mark generated content with `<!-- AUTO-GENERATED -->`
