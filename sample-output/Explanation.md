## Output of this session

| Agent | What it produced | Where |
|---|---|---|
| **@chote** (clerk) | The case diary with this week's hearing notes, a calendar event for the hearing, and a PREP reminder event 7 days before it | `diary.md` and the connected calendar |
| **@ustaad** (researcher) | Legal sources fetched live from the internet, each with its URL. Suggestions are saved first. Once the senior lawyer approves one, it is copied across so the drafter can use it | `repo/suggested.md`, then `repo/approved.md` |
| **@drafter** | The final draft as a Word file and a PDF, using only approved citations | `out/` |
| **@counter** (reviewer) | No file. Its output is the review report posted in the room: verified or mismatched citations, flaws and cross-questions for the drafter | Mattermost room |

### Notes
- Nothing is cited unless the senior lawyer approved it. The drafter reads only `repo/approved.md`.
- @counter produced no file in this session because its work is the review itself. It saves nothing unless you ask it to.
- All case data is fictional and used for demonstration only.