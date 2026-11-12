---
name: trigglo
description: Make product photos, short product videos and social posts for an online store with Trigglo, then schedule or post them to Instagram, Facebook and Threads. Use when someone asks for product photography, a product video, captions or a posting schedule for their store and Trigglo is connected (MCP server https://trigglo.com/mcp).
---

# Trigglo

Trigglo turns a store's own product photos into professional photos and 8-second videos, writes the captions, and posts them to the store's social channels. Its MCP server is `https://trigglo.com/mcp`; the person signs in to Trigglo once when connecting.

## Start with get_account

Call `get_account` first in a conversation. It returns the workspace, how many photos and videos are left this month, the workspace timezone, connected channels, and channels that need reconnecting. Mention the allowance before making a lot at once.

## Making photos

1. Find the product with `list_products` (search by name). If it isn't there, use `add_product`: with a public image link it is added at once; without one, apps that show Trigglo's cards show an upload box.
2. Pick scenes from `list_scenes`, or use `auto` to let Trigglo design one. For seasonal photos, pass a holiday id from `list_scenes`; it applies to every photo in the call.
3. Call `create_photos` with up to 4 photos. Each uses one from the monthly allowance.
4. Photos take about a minute. If the photos card is showing, it updates by itself. Otherwise poll `get_post` with each id until `status` is `ready` or `failed`.
5. Show the photos and their captions, then offer to schedule them.

## Videos

`create_video` makes one 8-second video of a product and takes two to four minutes. Poll `get_post` the same way.

## Posting

- Only schedule or post when the person asks. Confirm what goes out and when before calling `publish_now`.
- `schedule_post` takes an optional `at` time (ISO 8601 with a UTC offset, photos only); without it the post takes the next posting slot. `publish_now` posts at once. `unschedule_post` cancels.
- Posting from chat reaches Instagram, Facebook and Threads. TikTok, Pinterest and YouTube come back under `reviewInTrigglo` with a link: give the person that link.
- After scheduling, tell the person which channels each post goes to and when, in the workspace timezone.

## Captions and redos

- Trigglo writes the captions. Use `update_caption` only when the person asks for a change, and keep their wording.
- `redo_photo` makes a new version and uses one from the allowance. When the person says what was off, pass reasons: `product_wrong`, `lighting`, `colors`, `background` or `busy`.

## Channels

`list_channels` shows each channel and whether it is connected. To connect one, call `connect_channel` and give the person the link, or let them use the channels card's Connect button.

## When something is refused

Refusals come back as one plain sentence (allowance used, too many calls, not found, trial paused). Pass it on as it is, and don't retry in a loop.

More: https://trigglo.com/docs (tool reference: https://trigglo.com/docs/tools.md).
