# Trigglo for Claude

Product photos, short product videos and social posts for your online store, made and scheduled
from a conversation with Claude.

This repository is a Claude plugin marketplace with one plugin, **trigglo**. It connects Claude to
your Trigglo account (the MCP server at `https://trigglo.com/mcp`) and adds a skill that shows Claude
how to use it well: check your account first, make photos of your own products, wait until each one
is ready, and ask before anything is posted.

## Install

**Claude Code**

In a session (Claude Code 2.1.275 or later):

```
/plugin install trigglo --marketplace trigglo/agent-kit
```

Or from your shell:

```
claude plugin marketplace add trigglo/agent-kit
claude plugin install trigglo@trigglo
```

Then run `/mcp`, pick the Trigglo server and sign in to your Trigglo account in the browser.

**Claude on the web, the desktop app and Cowork**

1. Go to **Customize > Plugins > Add > Add marketplace > Add from a repository**, enter
   `trigglo/agent-kit` and click **Sync**.
2. Add the **Trigglo** plugin.
3. Open the plugin's **Connectors** tab, add Trigglo and connect it. You sign in to your Trigglo
   account, or create one, and approve what Claude may do.

Prefer not to use a plugin? Add Trigglo as a custom connector instead:
https://trigglo.com/ai/claude

## Things to ask

- "Make 4 photos of my newest product in a gift box scene."
- "What's going out on my social channels this week?"
- "Connect Instagram to Trigglo."

Photos take about a minute each. Claude posts or schedules only when you ask, to Instagram,
Facebook and Threads; TikTok, Pinterest and YouTube posts are reviewed in Trigglo first.

## What it sends

The plugin holds no code that runs on your computer: one skill (written instructions) and the
address of Trigglo's server. When you use it, Claude sends Trigglo your requests, for example a
product name, a product photo, a scene, a caption or a time to post, and Trigglo replies with your
products, photos, videos, captions and schedule. Details are in section 5 of the privacy policy:
https://trigglo.com/privacy#ai-apps. You can disconnect Claude at any time in Trigglo under
**Settings > AI apps**.

## Help

Docs: https://trigglo.com/docs. Email: hello@trigglo.com.

## License

The files in this repository are MIT licensed (see `LICENSE`). Using Trigglo is covered by its
terms: https://trigglo.com/terms.
