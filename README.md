# Devnator

Turns a project's README/docs (or a tutorial topic) into a complete narrated
video production package: 10 topic ideas, a continuous narration script, an
ElevenLabs voiceover, a beat-by-beat breakdown, one image prompt per beat as a
bulk-ready `.txt` file, a universal video-animation prompt, and thumbnail
prompts.

Runs as a strict state machine: one state at a time, always stops and waits
for your reply before moving on. Invoke it with `/devnator` once installed.

## Install

### One-liner (any agent that supports the `skills` npm package)

```bash
npx skills add samiul000/devnator
```

This clones the repo, finds `devnator/SKILL.md`, and copies it into the
correct skills directory for whichever agent you're running it from.

### Claude Code / Cowork

```bash
mkdir -p ~/.claude/skills/devnator
cp devnator/SKILL.md ~/.claude/skills/devnator/SKILL.md
```

Use `.claude/skills/devnator/` instead of `~/.claude/skills/devnator/` if you
want it scoped to one project (and shareable via git) rather than global.
Restart the session, then invoke with `/devnator` or just describe the task.

### Claude.ai

Zip the `devnator/` folder and go to \*\*Settings → Customize → Skills →

- Create skill → Upload\*\*. Invoke with `/devnator` or by describing the task.

### OpenAI Codex CLI

```bash
mkdir -p ~/.codex/skills/devnator
cp devnator/SKILL.md ~/.codex/skills/devnator/SKILL.md
```

Restart Codex to reload skill metadata. Use `.codex/skills/devnator/` or
`.agents/skills/devnator/` instead for a project-scoped install.

### opencode

opencode uses flat command files rather than `SKILL.md` folders. Strip the
frontmatter fence if you like, but it works fine as-is:

```bash
mkdir -p .opencode/command
cp devnator/SKILL.md .opencode/command/devnator.md
```

Or globally at `~/.config/opencode/command/devnator.md`. Invoke with
`/devnator` (opencode commands are always manual, no auto-trigger).

### ChatGPT

No native slash-command or skill-file system. Paste the body of
`devnator/SKILL.md` (everything below the `---` frontmatter block) into a
Custom GPT's Instructions field, or into a Project's custom instructions.
You invoke it by opening that GPT/Project rather than typing `/devnator` in
an ordinary chat.

## Updating

Edit `devnator/SKILL.md` and re-run whichever install step above applies, or
re-run `npx skills add <your-github-username>/devnator` to pull the latest
version.
