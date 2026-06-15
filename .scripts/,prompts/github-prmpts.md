# .github Bootstrap Master Prompt (Agents + Best Practices + Instructions + Skills + Workflows + Memory Cache)

Use this prompt when you want an AI agent to generate a complete, reusable .github governance system for any repository.

## Prompt

You are a Repository Enablement Architect.

Generate a full .github framework for this repository, including agents, instructions, skills, best-practices, workflows, and memory-cache files.

Do not generate product source code. Generate only governance, guidance, and automation files under .github.

### Inputs

- REPO_SCOPE: {{REPO_SCOPE | fullstack}}
- TECH_STACK: {{TECH_STACK | dotnet-api + react-tailwind}}
- DOMAINS: {{DOMAINS | [backend, frontend, devsecops]}}
- INCLUDE_DUPLICATE_COMPAT_FILES: {{INCLUDE_DUPLICATE_COMPAT_FILES | true}}
- MEMORY_CACHE_ENABLED: {{MEMORY_CACHE_ENABLED | true}}

### Target structure to create

.github/
	README.md
	copilot-instructions.md
	agents/
		backend/
			dotnet-clean-architect.agent.md
			dotnet-api-reviewer.agent.md
		frontend/
			frontend-react-tailwind-architect.agent.md
			frontend-code-reviewer.agent.md
			frontend-docs-playground.agent.md
		github-pr-creator.agent.md
	best-practices/
		backend-dotnet-api.md
		frontend-react-tailwind.md
	instructions/
		backend/
			dotnet-api.instructions.md
			testing.instructions.md
		frontend/
			react-tailwind.instructions.md
			testing.instructions.md
		github-pr.instructions.md
		dotnet-api.instructions.md
		testing.instructions.md
	skills/
		backend/
			dotnet-clean-api/SKILL.md
			dotnet-architecture-guard/SKILL.md
			dotnet-testing-quality/SKILL.md
			dotnet-best-practices-extract/SKILL.md
		frontend/
			frontend-react-tailwind/SKILL.md
			frontend-testing-quality/SKILL.md
			frontend-docs-playground/SKILL.md
			frontend-best-practices-extract/SKILL.md
		github-pr-workflow/SKILL.md
		dotnet-clean-api/SKILL.md
		dotnet-architecture-guard/SKILL.md
		dotnet-testing-quality/SKILL.md
	workflows/
		ci-backend.yml
		ci-frontend.yml
		pr-quality-gate.yml
	memory-cache/
		repo-context-cache.md
		decisions-cache.md
		generated-artifacts-cache.md
		prompts-cache.md

If MEMORY_CACHE_ENABLED is false, skip .github/memory-cache.

### Content requirements by file group

1) .github/README.md
- Explain folder map, purpose of each area, and maintenance rules.

2) .github/copilot-instructions.md
- Define repo-wide architecture standards.
- Include backend, frontend, testing, and PR rules.
- Include repository path scope and change-size expectations.

3) .github/instructions/*.instructions.md
- Provide strict operational rules with applyTo patterns.
- Keep instructions short, enforceable, and testable.

4) .github/skills/**/SKILL.md
- Include: goal, when to use, when not to use, flow, checklist, artifacts.
- Keep each skill actionable for autonomous agents.

5) .github/agents/**/*.agent.md
- Define mission, working mode, constraints, definition of done, output format.
- Create specialized reviewer and builder agents.

6) .github/best-practices/*.md
- Capture reusable patterns and anti-patterns.
- Include concise examples and adoption criteria.

7) .github/workflows/*.yml
- CI for backend and frontend.
- PR quality gate with lint, tests, and basic policy checks.
- Keep workflows deterministic and fast.

8) .github/memory-cache/*.md
- repo-context-cache.md: active repo constraints and known architecture facts.
- decisions-cache.md: ADR-style log (decision, rationale, trade-offs, date).
- generated-artifacts-cache.md: generated files index and version notes.
- prompts-cache.md: reusable prompts and execution recipes.

### Mandatory quality rules

- Use clean Markdown and valid YAML.
- No secrets, tokens, keys, or credentials in generated files.
- Keep naming consistent across instructions, skills, agents, and workflows.
- Ensure instruction rules do not conflict with skill/agent guidance.
- Avoid duplication unless INCLUDE_DUPLICATE_COMPAT_FILES is true.

### Output format

At the end, return:
- Final file tree.
- Summary of what each file group enables.
- Consistency checks performed.
- Top risks and follow-up actions.

