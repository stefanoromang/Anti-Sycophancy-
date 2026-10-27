# Anti-Sycophancy

A ruthless reality-check prompt that stops AI assistants from flattering you and makes them test, quantify, and rebuild your ideas instead.

The prompt lives in [`prompt.md`](prompt.md). **Edit only that file.**

## How it loads automatically

`prompt.md` is copied into every instruction file that AI coding tools read on their own when they open a repository:

| Tool | File loaded automatically |
|---|---|
| OpenCode, OpenAI Codex, Cursor, Zed, Jules, and other `AGENTS.md` tools | `AGENTS.md` |
| Claude Code | `CLAUDE.md` |
| Gemini CLI | `GEMINI.md` |
| GitHub Copilot | `.github/copilot-instructions.md` |
| Cursor (project rule) | `.cursor/rules/anti-sycophancy.mdc` |
| Windsurf | `.windsurf/rules/anti-sycophancy.md` |
| Cline | `.clinerules/anti-sycophancy.md` |

When `prompt.md` changes on `main`, a GitHub Action (`.github/workflows/sync.yml`) regenerates all of these files. To regenerate locally, run:

```bash
./scripts/sync.sh
```

## Chat apps (ChatGPT, Claude.ai, Gemini web)

Chat apps do not run instructions from an attached repository on their own. They treat attached files as reference material. To apply the prompt every time:

- **ChatGPT:** Paste `prompt.md` into *Settings → Personalization → Custom instructions*, or into a Project's or Custom GPT's instructions.
- **Claude.ai:** Create a Project and paste `prompt.md` into the project instructions.
- **Gemini:** Create a Gem and paste `prompt.md` into its instructions.

To use it once, attach the repo and start your message with: *"Follow prompt.md in this repo as your system instructions for this conversation."*

## Using it in other projects

These files only take effect inside this repository. To apply the rules everywhere:

- **Claude Code:** copy `CLAUDE.md` to `~/.claude/CLAUDE.md`
- **OpenCode:** copy `AGENTS.md` to `~/.config/opencode/AGENTS.md`
- **Codex:** copy `AGENTS.md` to `~/.codex/AGENTS.md`
- **Gemini CLI:** copy `GEMINI.md` to `~/.gemini/GEMINI.md`
