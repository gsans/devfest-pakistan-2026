# DevFest Pakistan 2026: Agentic Engineering with ADK and MCP

Labs, solutions and demos from the talk, to run at your own pace.

**Hub:** [linktr.ee/devfest_pakistan](https://linktr.ee/devfest_pakistan)

## Setup (~15 min)

### 1. Get a Google AI Studio API key

1. Go to [aistudio.google.com/apikey](https://aistudio.google.com/apikey) and sign in with your Google account.
2. Click **Create API key** and copy it.
3. Keep it private. Don't post it anywhere or commit it to Git.

> [!WARNING]
> **Free keys get about 60 requests a day with Gemini 3.5 Flash Lite, the model the labs use.** One question to a lab agent uses 2 to 6 requests.

### 2. Get the repo and check your key

You need [Node.js](https://nodejs.org) v20 or newer and Git. Open a terminal and run these one at a time:

```bash
git clone https://github.com/gsans/devfest-pakistan-2026.git
```
```bash
cd devfest-pakistan-2026
```
```bash
npm install
```

> [!TIP]
> `npm install` downloads about 380 MB and can take a few minutes.

```bash
cp .env.example .env
```

On Windows Command Prompt, use `copy .env.example .env`.

Open the new `.env` file, replace `your-api-key-here` with your key, and save. Then run:

```bash
npm run verify
```

✅ **Done** when you see `Ready for labs`. If you see ❌, the message tells you what to fix.

## Run the labs

```bash
npm run web
```

Open [http://localhost:8000](http://localhost:8000) and pick a lab from the dropdown. If port 8000 is taken, run `npm run web -- -p 8123` instead.

| Lab | What it shows | Try |
|---|---|---|
| `01-tools` | An agent calling local functions | `What is 21 + 21?` |
| `02-mcp` | The same tools moved to MCP servers | `What's the weather in Islamabad?` |
| `03-sequential` | Agents in a fixed sequence, sharing state | `Compare London and Islamabad` |
| `04-deep-research` | Planner, researcher and writer, with 3 TODOs for you | `How do MCP and A2A differ?` |
| `04-deep-research-solution` | The finished version of lab 4 | `How do MCP and A2A differ?` |

Each lab's README has the details and an optional task. You can do the optional tasks by hand or with a coding agent such as [Antigravity](https://antigravity.google/download).

To run the finished optional tasks:
```bash
npx adk web solutions --bundle false
```

## Mission Control demo

The Axiom Software Factory from the closing demo: a coding agent in its own Git worktree, a human gate, deterministic checks and an independent reviewer, driven by clicks or voice. It needs Python as well as Node. [Run it yourself](./mission-control/README.md).

## Reading (optional)

* [Slow Engineering Field Manual (PDF)](./manuals/Slow-Engineering-Field-Manual-Gerard-Sans.pdf)

## What's in the repo

* `labs/`: the four ADK labs, plus the lab 4 solution
* `solutions/`: finished optional tasks and the `whiteboard-info` skill
* `notebooks/`: reference notebooks (read-only)
* `mission-control/`: the Mission Control demo, with its own setup
* `manuals/`: the field manual
* `verify.mjs`: the key check that `npm run verify` runs
