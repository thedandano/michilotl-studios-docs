---
title: Support — World Cup Bar
---

# Support

## Frequently asked questions

### The menu bar shows "Live data unavailable"

World Cup Bar couldn't reach the match data API. This usually means:

- Your device is offline.
- The worldcup26.ir data source is temporarily unavailable.

The app retries automatically. If cached data is available from a previous successful fetch, it shows that instead.

### The menu bar shows "World Cup" with no score

No match involving a followed country is currently live or imminent. The app shows the next upcoming tournament fixture as a fallback, or this label if there are no upcoming matches found.

Check **Settings → Followed Countries** to make sure you're tracking the teams you care about.

### The menu bar shows "See you in 2030!"

The 2026 World Cup tournament is complete. No more fixtures remain. The app will remain installed but will not show live data until a future update covers the next tournament.

### Scores seem delayed or out of date

During live matches the app refreshes every 30 seconds. If the refresh button (↺) in the dropdown is spinning, a refresh is already in progress. Tap it again once it's idle to request a manual refresh.

### How do I turn off analytics?

Go to **Settings → Analytics** and toggle off **Usage analytics**. The setting is saved immediately and persists across restarts.

### Where is my data stored?

Followed countries and display preferences are stored in `UserDefaults` on your Mac. The last known match snapshot is cached at `~/Library/Application Support/WorldCupBar/snapshot-cache.json`. Nothing is uploaded to Michilotl Studios servers.

### I bought this — what does my purchase include?

World Cup Bar is a one-time purchase covering the 2026 FIFA World Cup season. It is not a subscription and does not auto-renew. All features are available from the moment of purchase. No future updates are guaranteed beyond the 2026 tournament.

## Contact

For anything not covered here, email [support@michilotl.com](mailto:support@michilotl.com). Include your macOS version and a brief description of the issue.
