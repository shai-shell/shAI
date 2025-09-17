# shAI — Bring AI to your shell

Turn plain English into safe, correct CLI commands on macOS. Install the shell plugin, press Cmd+Return, and let the LLM produce the exact command you need.

## Quick start (3 steps)

1) Sign up: [shai.sh](https://shai.sh)

2) Install shell plugin client (one‑liner in your terminal). The installer runs in about 5 minutes.
```bash
curl -fsSL https://github.com/shai-shell/shAI/releases/latest/download/install.sh -o /tmp/install.sh && bash /tmp/install.sh
```
- Open a new terminal tab (or restart) so keybindings initialize

3) Sign in:
```bash
shai login
```
You are all set. Jump to Try it below.

## Prerequisites (macOS)

- macOS 12 or later
- Supported terminals: iTerm2 or Terminal.app
- Internet connection
- Tools: `curl`, `bash`, and `zsh`

## Sign up

Create your account at [shai.sh](https://shai.sh) using email or OAuth (GitHub or Google). Email verification is required.

## Install the shell plugin (macOS)

Run the one‑liner above in your terminal. Then:

- Open a new iTerm2/Terminal tab so keybindings initialize
- In some cases, restarting your terminal emulator (or your computer) may be required
- iTerm2 may ask for Automation permission. Click "OK". If previously denied, enable it in:
  System Settings → Privacy & Security → Automation → iTerm → System Events

About the installer:
- Installs the shell plugin, Helper, and required dependencies
- Does not modify PATH or remove anything existing from your system
- Adds the shell plugin to your `.zshrc`

## Sign in (terminal) & verify

Connect your terminal to your account:
```bash
shai login
```

Verify:
```bash
shai status
```

Expected:
- Logged in
- Helper: running

## Try it

The LLM returns a command you can run. Review before executing.

- Ask LLM a question:
  ```bash
  command to list files larger than 5MB
  ```
- Send using: Cmd+Return

## Essential keybindings

- Cmd+Return — Ask LLM something
- Cmd+↑ / Cmd+↓ — Browse command/response history
- Tab / Shift+Tab — Expand/collapse command/response recall

## Navigate recent answers and commands

- Cmd+↑ / Cmd+↓: move through recent entries (current session)
- Tab: expand a long/multi‑line response in place
- Shift+Tab: collapse back to a single‑line preview

> Pro tip: When you land on a recalled response, you can edit it immediately and press Return to execute.

## Change LLM provider or model

Edit:
```bash
~/dev/shai/config/config.yaml
```
- Uncomment `ai.provider` and set to a supported provider under `ai.providers`
- Uncomment `ai.model` and choose a model supported by that provider

## Keybinding customization (optional)

You don’t need to change anything to get started. If you want to customize:

- User config (macOS):
  ```bash
  ~/Library/Preferences/shai/config.yaml
  ```
- After changes, open a new terminal tab/window to re‑initialize keybindings.

Example: override keybindings for iTerm2
```yaml
terminals:
  iterm2:
    keybindings:
      # Ask AI (Cmd+Return) – default CSI sequence shown for reference
      llm: "^[[13;9u"
      # History up/down (Cmd+↑/↓)
      navigate_up: "^[[126;9u"
      navigate_down: "^[[125;9u"
```

Tip: Find keybinding codes by running `cat -v` and pressing the desired combination.

## Troubleshooting

One‑stop diagnostics:
```bash
shai debug
```

Checks over 50 items across these areas:
- Plugin version and configuration
- System dependencies
- Helper process
- Terminal functionality
- Keybindings

Common fixes:
- Special keys not working:
  - Open a new terminal tab
  - Verify keybindings and Helper via `shai debug`
  - Try rebooting
- Helper issues:
  - Try rebooting
- Sign‑in issues:
  - Make sure you completed sign‑up at [shai.sh](https://shai.sh), including email verification
- Slow/no responses:
  - Check Helper via `shai debug`
  - Check your network connectivity

Where things live:
- User config (macOS): `~/Library/Preferences/shai/config.yaml`
- Runtime/logs: `~/.shai/run/` — `debug.log`, `daemon.log` (share only if asked)

## Maintenance

Update anytime:
```bash
shai update
```

Uninstall:
```bash
shai uninstall
```

Uninstall cleans up everything and leaves no trace.

## Privacy

shAI uses your question plus recent terminal context to generate helpful, accurate answers. Avoid including secrets or sensitive information in your prompt or pasted text.

## Feedback & support

Send quick feedback from the terminal (we encourage you to use GitHub Discussions so everyone can benefit):
```bash
shai feedback "Feedback message here"
```

- General and Feedback — Chat about anything and everything. [Open discussion](https://github.com/shai-shell/shAI/discussions/new?category=general-and-feedback)
- Help — Ask the community for help. [Get help](https://github.com/shai-shell/shAI/discussions/new?category=help)
- Ideas — Share ideas for new features. [Share an idea](https://github.com/shai-shell/shAI/discussions/new?category=ideas)

