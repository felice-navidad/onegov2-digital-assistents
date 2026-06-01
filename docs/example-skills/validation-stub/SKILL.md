---
name: validation-stub
description: Minimal starter for a validation Skill that judges whether other Skills in this repository are correctly built against the Raamwerk van de Digitale Assistent. Use as a starting point when designing the optional validation-Skill extension from the challenge brief. Not a finished Skill, fill in the gaps.
---

# Validation Skill, starter stub

This is a **stub**, not a finished Skill. It exists so teams that pick the
optional validation-Skill extension (see [CHALLENGE.md](../../../CHALLENGE.md#guiding-research-questions))
have a concrete starting point.

If you want a fully worked validator, see
[../framework-validator/SKILL.md](../framework-validator/SKILL.md). This
stub is intentionally smaller and more opinionated about what to fill in.

## When to use this Skill

Trigger when the user asks "is this Skill correctly built?", "validate
skills/", or "does this Skill follow the framework?". Decide explicitly
whether your validator covers:

- structural conformance (frontmatter, naming, links), or
- substantive conformance (does the Skill actually reflect the framework
  domain it claims to cover), or
- both.

## What to do

Fill in the steps below for the validator you want to build.

1. **Locate the Skill(s) to check.** TODO: describe how the agent finds
   the target (single directory, all of `skills/`, a glob from the user).
2. **Run mechanical checks.** TODO: list the structural rules you enforce.
   Reuse `python scripts/lint_skill.py` if you want; that is the
   repository-level linter, not a Skill.
3. **Run substantive checks.** TODO: describe how you verify the Skill
   maps to one or more files under `content/domains/` or
   `content/practices/`, and how strict the mapping must be.
4. **Report findings** per Skill, ending with a verdict (`ready`,
   `needs-fix`, or `blocked`).

## Conventions to enforce

TODO: list the rules you commit to, for example:

- Directory name matches frontmatter `name`.
- `description` answers both *what* and *when*.
- The Skill links to at least one file under `content/`.
- No tool-specific frontmatter without a clearly labelled fallback section.

## What to avoid

- Do not silently rewrite Skills. Report and let the author fix.
- Do not depend on tool-specific behaviour (allowed-tools, hooks, etc.) in
  the validator's own instructions, that defeats the point.
- Do not duplicate `scripts/validate.py`. That script is a repo linter,
  not a Skill. A validation Skill is a portable instruction set the agent
  can follow in any compatible tool.

## Additional resources

- [docs/skill-format.md](../../skill-format.md), the format spec.
- [docs/skill-checklist.md](../../skill-checklist.md), the human checklist.
- [content/domains/](../../../content/domains/) and [content/practices/](../../../content/practices/),
  the source-of-truth your validator references.
