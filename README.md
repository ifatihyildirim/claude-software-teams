# Claude Code Software Teams

Ready-to-use software team agent definitions for Claude Code. Two separate teams included:

## Mobile App Team

Cross-platform mobile app development team.

**Tech Stack:** Expo + React Native + NativeWind + TypeScript

| Agent | Role | File |
|-------|------|------|
| `mobile-lead` | Team Lead | `.claude/agents/mobile-lead.md` |
| `mobile-dev` | Mobile Developer | `.claude/agents/mobile-dev.md` |
| `mobile-backend` | Backend Developer | `.claude/agents/mobile-backend.md` |
| `mobile-designer` | UI/UX Designer | `.claude/agents/mobile-designer.md` |
| `mobile-qa` | QA Engineer | `.claude/agents/mobile-qa.md` |

## Landing Page Team

Landing page / corporate site development team.

**Tech Stack:** Next.js 14+ (App Router) + Tailwind CSS + TypeScript

| Agent | Role | File |
|-------|------|------|
| `web-lead` | Team Lead | `.claude/agents/web-lead.md` |
| `web-frontend` | Frontend Developer | `.claude/agents/web-frontend.md` |
| `web-backend` | Backend Developer | `.claude/agents/web-backend.md` |
| `web-designer` | Designer | `.claude/agents/web-designer.md` |
| `web-qa` | QA Engineer | `.claude/agents/web-qa.md` |

## Setup

1. Clone this repo or copy the `.claude/agents/` directory into your project:

```bash
git clone https://github.com/ifatihyildirim/claude-software-teams.git
# or copy just the agents folder into an existing project
cp -r claude-software-teams/.claude/agents/ your-project/.claude/agents/
```

2. Open Claude Code in your project directory — agents are automatically discovered from `.claude/agents/`.

## Usage with Claude Code CLI

### Using a Single Agent

You can reference any agent by its filename (without `.md`) when asking Claude Code to spawn an agent:

```
> Use the mobile-dev agent to build a login screen
> Use the web-frontend agent to create a hero section
```

Claude Code will use the Agent tool internally with the custom agent type:

```
Agent(subagent_type="mobile-dev", prompt="Build a login screen...")
```

### Creating a Team

Ask Claude Code to create a full team for coordinated work:

```
> Create a mobile-app-team and spawn all mobile agents
```

This triggers the following workflow:

#### Step 1 — Create the team

```
TeamCreate(team_name="mobile-app-team", description="Mobile app development")
```

#### Step 2 — Create tasks

```
TaskCreate(subject="Set up Expo project", description="Initialize Expo project with TypeScript and NativeWind...")
TaskCreate(subject="Design login screen", description="Create login screen design with form fields...")
TaskCreate(subject="Build auth API", description="JWT-based authentication endpoints...")
```

#### Step 3 — Spawn teammates

Each agent is spawned with its custom agent type and assigned to the team:

```
Agent(
  name="mobile-lead",
  subagent_type="mobile-lead",
  team_name="mobile-app-team",
  prompt="You are the Mobile Team Lead...",
  run_in_background=true
)

Agent(
  name="mobile-dev",
  subagent_type="mobile-dev",
  team_name="mobile-app-team",
  prompt="You are the Mobile Developer...",
  run_in_background=true
)

# ... repeat for mobile-backend, mobile-designer, mobile-qa
```

#### Step 4 — Assign tasks

```
TaskUpdate(taskId="1", owner="mobile-dev", status="in_progress")
TaskUpdate(taskId="2", owner="mobile-designer", status="in_progress")
TaskUpdate(taskId="3", owner="mobile-backend", status="in_progress")
```

#### Step 5 — Communicate

Agents communicate via messages:

```
SendMessage(type="message", recipient="mobile-dev", content="Login screen design is ready, check task #2")
SendMessage(type="broadcast", content="Sprint goal updated")
```

### Running Two Teams

Claude Code can only manage one team at a time. To work with both teams:

1. Create and work with the first team (e.g., `mobile-app-team`)
2. Shut down the first team when done
3. Create and work with the second team (e.g., `landing-page-team`)

### Using Worktree Isolation

For parallel work without conflicts, agents can run in isolated git worktrees:

```
Agent(
  name="mobile-dev",
  subagent_type="mobile-dev",
  team_name="mobile-app-team",
  isolation="worktree",
  prompt="Build the login screen..."
)
```

## Customization

Each `.md` file defines:

- **Role** — What the agent does
- **Tech Stack** — Tools and libraries it works with
- **Responsibilities** — Specific tasks it handles
- **Guidelines** — Rules and best practices it follows
- **Code Style** — Formatting and convention preferences

Edit any `.md` file to adjust the agent's behavior, add new tools, or change conventions to match your project.
