# Chambers: a virtual law chambers in one chat room

A solo lawyer's team of AI agents and a junior lawyer in one Mattermost room, connected with Switch. The lawyer approves every step. DRAFT outputs are for lawyer review and are not legal advice.

## How Switch is used
Switch Console runs four Claude Code agents on the lawyer's own machine and puts them in a Mattermost room with the lawyer and a junior. Agents hand work to each other with @mentions, and the room log is the shared record. Without Switch, these would be four disconnected scripts.

## Agents
| Agent | Role |
|---|---|
| @chote | Clerk: saves hearings, creates calendar events and a 7-day prep reminder, keeps hearing notes |
| @ustaad | Researcher: fetches real public legal sources live, cites the URL and section, suggests them for approval |
| @drafter | Drafts applications to Word and PDF using only approved citations |
| @counter | Reviews drafts, verifies citations by re-fetching them, cross-questions, and sends flaws back (max 2 rounds) |

## Flow
chote (hearing + calendar) → ustaad (laws) → lawyer approves → drafter (draft) → counter (review) → drafter (revise) → lawyer's final review

## Setup
1. Install Switch Console and Docker: https://github.com/sandbox-quantum/switch/releases/latest
2. Sign in to Claude Code on your machine.
3. Connect Mattermost (Switch Console sets up a local one) and create a junior-lawyer user.
4. Create the four agents in Console (Your Agents → New agent), using the prompts in `agents/`. Set "Who can talk to your agent" to "Only me and my agents" (and allow the junior).
5. In your agent folder, create a Python venv and run `pip install -r requirements.txt`.
6. Add the agents to your room and post the start message from the demo.

## What is real and what is not
- Real: live web fetching of public legal sources, calendar creation, Word and PDF generation.
- Agents can make mistakes. Verify every citation against its URL.

## Demo video
[link]
