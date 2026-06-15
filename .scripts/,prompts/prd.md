I want you to generate a project structure inside a root folder called `.projects`.

You must create 3 management applications:

1. TaskFlow Pro
Advanced personal and team task management application.
It must include priorities, dependencies, due dates, subtasks, tags, checklists, comments, attachments, automation rules, Kanban, calendar, timeline, focus mode, and productivity metrics.

2. Habit + Goals Manager
Application to manage daily habits and weekly/monthly goals.
It must include recurring habits, measurable goals, streaks, goal health, a dashboard with charts, weekly comparisons, and smart notifications.

3. Personal Finance Organizer
Simple personal finance management application.
It must include income, expenses, budgets, savings goals, deviation alerts, a savings simulator, and a visual dashboard.

Required structure:

.projects/
  taskflow-pro/
    prd.md
    epics/
    tasks/
    cache/
    status.md

  habit-goals-manager/
    prd.md
    epics/
    tasks/
    cache/
    status.md

  personal-finance-organizer/
    prd.md
    epics/
    tasks/
    cache/
    status.md

For each project, generate:

1. A `prd.md` file with:
- product vision
- problem statement
- target users
- main features
- user flow
- initial data model
- functional requirements
- non-functional requirements
- success metrics
- risks
- MVP roadmap

2. In the `epics/` folder, create separate epic files in Markdown:
- backend.md
- frontend.md
- devsecops.md

3. In the `tasks/` folder, create separate task files by area:
- backend-tasks.md
- frontend-tasks.md
- devsecops-tasks.md

Each task must include:
- ID
- title
- description
- priority
- dependencies
- acceptance criteria
- estimate
- initial status: `todo`

4. In the `cache/` folder, create:
- context-cache.md
- decisions-cache.md
- generated-artifacts.md

The cache must be used to reuse internal context and avoid repeating unnecessary information in future executions.

5. Create a `status.md` per project with:
- current summary
- progress percentage
- last executed action
- next steps
- blockers
- last updated date

Important rules:
- Do not implement code yet.
- Only generate product documentation, epics, tasks, cache, and status.
- Keep a clear structure so an agent can continue the work without consuming too many tokens.
- Use clean Markdown.
- Prioritize an architecture ready for frontend, backend, and DevSecOps.
- Design the projects as modern SaaS applications.