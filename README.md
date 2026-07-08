# Creative Brief — a Claude skill that writes my weekly marketing brief

A Claude Code plugin/skill that scans current LinkedIn and Instagram trends, maps them to [Upskill PM](https://www.upskillpm.org)'s three audiences (career-switchers into PM, visa-track founders, current/future founders), and produces a structured creative brief: hook, core message, and target platform for each content angle.

## How it runs in production

This isn't a demo — it's my actual marketing pipeline, and a case study in *workflow automation as product management*:

```
Friday 5pm PT (scheduled task)
   └─► creative-brief skill
         ├─ scans LinkedIn/Instagram trends in my market
         ├─ maps trends → audience segments → content angles
         └─ outputs a structured Markdown brief
   └─► saved to Google Drive (dated doc)
   └─► Gmail draft to me — draft, not send: human reviews before anything ships
```

## Design decisions

1. **Audience mapping is explicit, not vibes.** The skill carries a fixed definition of the three audience segments, so every trend gets evaluated against *who it's for* — the same discipline you'd want in a human brief.
2. **Draft, don't send.** The automation stops one step before the outside world. AI drafts; a human approves. That's the right autonomy level for brand-facing output.
3. **Deliver twice, fail loud.** Output goes to both Drive (archive) and inbox (attention). If either delivery fails, the full brief lands in the run notification so the work is never lost.

## Structure of a brief

Each weekly brief contains 3–5 content angles, each with:
- **Trend** — what's moving on LinkedIn/Instagram right now, and why
- **Audience** — which of the three segments it speaks to
- **Hook** — the opening line that earns the stop-scroll
- **Core message** — the one thing the post must communicate
- **Platform** — where this angle will perform best, and in what format

## Built with

Claude Code skills (`SKILL.md` instruction format) · scheduled tasks · Google Drive + Gmail connectors (MCP)

---

*Part of my open AI PM portfolio — see [ai-pm-educator](https://github.com/aly-coding/ai-pm-educator) for the teaching agent and [ai-pm-toolkit](https://github.com/aly-coding/ai-pm-toolkit) for templates and guides.*
