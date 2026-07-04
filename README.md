# claude-code-skills

A small collection of [Claude Code](https://docs.claude.com/en/docs/claude-code) **Skills** I built and actually use — packaged so you can drop them into your own setup.

Most of them help me *think*: make a decision, pressure-test an idea from both sides, run a focused work session, or sit with something Stoic. Some help me *make* or *do*: turn a rough idea into a finished blog post, or translate a sentence between English and Polish with the register and nuance intact. They're not a framework or a product — just real tools from a working `~/.claude/skills/` folder, cleaned up and shared.

## What is a Claude Code Skill?

A Skill is the simplest way to extend Claude Code: a folder with a single `SKILL.md` file inside. The file has a bit of YAML frontmatter — a `name` and a `description` that tells Claude *when* to reach for the skill — followed by the instructions Claude should follow once it does.

```
skills/
  mental-models/
    SKILL.md      ← frontmatter (name + when-to-trigger) + the playbook
```

No code, no build step, no dependencies. Claude reads the `description`, decides on its own whether the skill is relevant to what you're doing, and — if so — loads the body and follows it. That "decides on its own" part is the whole craft: a skill lives or dies by how well its trigger conditions are written. Most of the work in the files below is in getting Claude to fire the skill at the right moment and *not* fire it at the wrong one.

## The skills

| Skill | What it does | Language | How it triggers |
|---|---|---|---|
| [**mental-models**](skills/mental-models/SKILL.md) | Coaches you through a hard decision using Naval Ravikant's mental models — surfaces the 2–3 that fit, asks the core question behind each, and leaves the conclusion to you. | English | Proactively, whenever a *decision* is the topic ("I'm going back and forth…", weighing a job / partnership / pivot). |
| [**cruciable**](skills/cruciable/SKILL.md) | Stress-tests an idea in a 3-round debate between an Advocate and a Devil's Advocate. Each round they must answer each other and add something new — no repeating arguments — then it closes with a synthesis and the real crux. | English | "debate this", "argue both sides", "steelman and criticize", "play devil's advocate", "run a cruciable". |
| [**thinking-partner**](skills/thinking-partner/SKILL.md) | Runs a focused ~10-minute thinking session: one question at a time, stays on scope, ends with a single concrete next step. | English / Polish | "thinking session", "let's do a session", "10 minutes", "pomóż mi przemyśleć". |
| [**stoic-mentor-en**](skills/stoic-mentor-en/SKILL.md) | A Socratic Stoic mentor — asks rather than answers, drawing on Marcus Aurelius, Epictetus, Seneca, and modern Stoics (Holiday, Pigliucci, Robertson). | English | "stoic session", "talk to a stoic", "stoic mentor". |
| [**stoic-mentor**](skills/stoic-mentor/SKILL.md) | The same Stoic mentor, in Polish. | Polish | "askstoic", "sesja stoicyzmu". |
| [**write-post**](skills/write-post/SKILL.md) | Turns a raw idea or pasted draft into a publish-ready blog post — learns the blog's current voice and frontmatter first, proposes title/slug/excerpt options, then writes. | English | "write a post", "new blogpost", "draft a note", or pasting text to shape into a post. |
| [**translate-en-to-pl**](skills/translate-en-to-pl/SKILL.md) | Translates an English sentence into Polish the careful way: confirms the intent and register first, then offers three distinct options (faithful / natural / register shift), each with an example of use and a one-line reason. | English → Polish | "translate to Polish", "how do I say this in Polish", "przetłumacz na polski". |
| [**translate-pl-to-en**](skills/translate-pl-to-en/SKILL.md) | The mirror of the above, Polish → English — confirms tone, then three register-aware options with examples and reasons, recovering what Polish drops (subjects, gender, particles). | Polish → English | "translate to English", "przetłumacz na angielski", or pasting a Polish sentence. |

A few honest notes:

- **The Stoic mentor ships in two languages** — `stoic-mentor-en` (English) and `stoic-mentor` (Polish). They're the same skill; keep whichever you'll actually talk to, or both.
- **write-post is wired to my personal blog** (an Astro site with dated Markdown notes). It's the most project-specific skill here — shared as a worked example of how a skill can encode the exact conventions of *your* project, not because you'll use it verbatim.
- **These lean personal.** They encode *my* taste in how to think through things — which is the point of a good skill. Fork them and bend the questions to yours.

## Install

Skills live in `~/.claude/skills/`. To install all of them:

```bash
git clone https://github.com/jaal/claude-code-skills.git
cp -r claude-code-skills/skills/* ~/.claude/skills/
```

Or just one:

```bash
cp -r claude-code-skills/skills/cruciable ~/.claude/skills/
```

Restart Claude Code (or start a new session) and the skills are available. Claude will invoke them on its own when the trigger conditions match; you can also invoke one explicitly with `/mental-models`, `/cruciable`, and so on.

> Tip: skills also work per-project. Drop a skill folder in `<your-project>/.claude/skills/` to make it available only inside that repo.

## Anatomy of a good SKILL.md

If you want to write your own, these files are worth reading as examples of the same handful of choices, made deliberately:

- **The `description` is the most important line in the file.** It's the only thing Claude sees when deciding whether to use the skill. Every description here spells out concrete trigger phrases and — just as important — when *not* to fire (e.g. `cruciable` explicitly excludes simple factual questions; `thinking-partner` excludes open-ended chat and research).
- **Write the body as instructions to a colleague, not config.** "Ask exactly this question", "one question at a time", "the Advocate always opens each round". The more the body reads like a playbook, the more reliably Claude follows it.
- **Encode taste, not just steps.** The value in `mental-models` isn't "help me decide" — it's the specific rule to surface only 2–3 models, ask the core question behind each, and refuse to hand over the conclusion. In `write-post`, it's the rule to read the most recent posts first and match the blog's *current* voice, because the blog evolves.
- **Give the rules teeth.** `cruciable` only works because its rules are enforceable and checkable: three rounds, address-before-you-extend, never repeat an argument. Vague guidance produces vague behavior.
- **Show an example run.** Most of these end with a short sample dialogue. It anchors tone better than any amount of description.

## Why this exists

I build small tools for myself and write about them. This repo is one of those — the "tell" half of *build-and-tell*. If a skill here saves you five minutes or gives you a cleaner way to think through a decision, that's the whole point. PRs and forks welcome.

More of my writing lives at [olek.works](https://olek.works).

## License

[MIT](LICENSE) — use, adapt, and share freely.
