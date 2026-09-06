---
name: openclaw
description: Set up or troubleshoot the claude-mem plugin on an OpenClaw gateway.
---

# Claude-Mem for OpenClaw

The installer changes gateway configuration and starts services. Inspect the
current installation first, and run it only when the user asked to install,
upgrade, or reconfigure the plugin.

## Install or upgrade

For a normal installation:

```bash
curl -fsSL https://install.cmem.ai/openclaw.sh | bash
```

The installer checks dependencies, configures the plugin and memory slot, selects
an AI provider, starts the worker, and can configure an observation feed. It
supports `--non-interactive`, `--upgrade`, `--provider`, `--api-key`, and
`--branch`; use only the options needed for the user's request. From a complete
source checkout, `bash openclaw/install.sh` runs the same installer locally.

For manual setup, configuration fields, observation-feed targets, or detailed
troubleshooting, read the maintained
[OpenClaw integration guide](https://docs.claude-mem.ai/openclaw-integration).

## Verify

After configuration:

1. Restart the OpenClaw gateway.
2. Confirm `http://localhost:37777/api/health` responds successfully.
3. Check gateway logs for the claude-mem plugin load message.
4. Run `/claude_mem_status` in an OpenClaw chat.
5. Have an agent perform a small task and confirm its observation appears in the
   viewer at `http://localhost:37777`.

If an observation feed is enabled, run `/claude_mem_feed` and verify its
connection before expecting channel messages.
