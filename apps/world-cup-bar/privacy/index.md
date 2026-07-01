---
title: Privacy Policy — World Cup Bar
---

# Privacy Policy

**World Cup Bar** is a macOS menu bar app by Michilotl Studios.

**Effective date:** June 2026

## What we collect

### Optional product analytics

If you leave analytics enabled (the default), World Cup Bar sends anonymous usage signals to [TelemetryDeck](https://telemetrydeck.com). These signals include:

- App refresh events (started, succeeded, failed)
- Display mode changes (abbreviations vs. flags)
- Number of followed countries (count only, not which countries)

TelemetryDeck events do **not** contain personally identifiable information. Events are hashed on-device before transmission. You can read TelemetryDeck's privacy documentation at [telemetrydeck.com/privacy](https://telemetrydeck.com/privacy/).

You can turn analytics off at any time in **Settings → Analytics**.

### Crash reporting

If a DSN is configured (it is not in the default App Store build), World Cup Bar can send crash reports and API error breadcrumbs to [Sentry](https://sentry.io). The default App Store distribution does **not** include a Sentry DSN and therefore sends no crash data.

## What we do not collect

- No name, email address, or Apple ID.
- No location data.
- No device identifiers beyond what TelemetryDeck's on-device hashing produces.
- No browsing history or activity outside the app.
- No payment information (purchases are handled entirely by Apple).

## Local storage

World Cup Bar caches the most recent match snapshot to disk in your macOS Application Support folder (`~/Library/Application Support/WorldCupBar/snapshot-cache.json`). This file contains only the last-fetched match and team list from the public worldcup26.ir API. It is never uploaded anywhere.

Your followed-country codes and display preferences are stored in `UserDefaults` and remain on your device.

## Third-party data

Match data is fetched from the public [worldcup26.ir](https://worldcup26.ir) API. Michilotl Studios has no affiliation with that service and does not control its data practices.

## Contact

Questions about privacy? Email [support@michilotl.com](mailto:support@michilotl.com).
