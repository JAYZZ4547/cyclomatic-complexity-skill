# cyclomatic-complexity

A Claude skill that refactors code to reduce cyclomatic complexity. Built for AI-generated code: it works, but branches like a jungle. This skill makes Claude measure complexity, refactor hotspots, and keep code maintainable for humans and the long-term vision of the codebase.

## What it does

- Measures cyclomatic complexity per function (radon, eslint, gocyclo, lizard, or manual count)
- Respects your project's own linter thresholds when configured
- Refactors worst hotspots first: guard clauses, extract function, lookup tables, named predicates
- Refuses to game the metric. Complexity moves into well-named functions, not into clever one-liners
- Ends every refactor with a before/after complexity table

## Install

### Claude Code

```
/plugin marketplace add saurabhkumar8112/cyclomatic-complexity-skill
/plugin install cyclomatic-complexity@cyclomatic-complexity-skill
```

### Claude.ai

Download the `.skill` file from Releases (or zip the `skills/cyclomatic-complexity` folder) and upload it under Settings → Capabilities → Skills.

### Claude API

Upload via the [Skills API](https://docs.claude.com/en/api/skills-guide).

## Usage

Triggers automatically on refactoring, cleanup, and code review requests. Or invoke directly:

> "Use the cyclomatic complexity skill to refactor parser.py"

## Example output

```
## Complexity report
| Function | Before | After |
|----------|--------|-------|
| parseOrder | 14 | 4 |

Extracted: validateHeader, resolveDiscount
Behavior verified: existing test suite passes
```

## License

Apache 2.0
