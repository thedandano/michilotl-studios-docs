---
title: Ops — World Cup Bar
---

# Operational Setup

## Xcode project setup (required before shipping)

The codebase is a Swift Package Manager project. Open it in Xcode with:

```
xed /path/to/world-cup-kickoff-bar
```

### Signing

1. Select the `WorldCupBar` scheme.
2. In **Signing & Capabilities**, set your Team and Bundle ID (`com.michilotl.WorldCupBar`).
3. Under **Build Settings → Code Signing Entitlements**, point to `Sources/WorldCupBar/WorldCupBar.entitlements`.

### Info.plist

`Sources/WorldCupBar/Info.plist` is picked up automatically by Xcode. Bump `CFBundleVersion` (build number) before each archive. `CFBundleShortVersionString` is the user-visible version.

---

## Sentry crash reporting

Sentry Cocoa is not in `Package.swift` because its SPM product has a module interface incompatibility with `swift build`. Add it through Xcode:

1. **File → Add Package Dependencies…**
2. URL: `https://github.com/getsentry/sentry-cocoa.git`
3. Exact version: `9.17.1`
4. Add **SentrySPM** to the `WorldCupBar` target.
5. In `Sources/WorldCupBar/WorldCupMonitoring.swift`, restore the Sentry integration:
   - Add `import Sentry` at the top.
   - In `init`, reinstate `SentrySDK.start { ... }` guarded by `sentryDSN`.
   - Restore `SentrySDK.addBreadcrumb` calls in the telemetry methods.
   - Restore `SentrySDK.capture(error:)` in `recordRefreshFailed`.
6. Set the DSN at runtime via the `WORLD_CUP_BAR_SENTRY_DSN` environment variable, or embed it directly for the production build.

`MonitoringConfiguration` already reads the DSN from the environment — if it is absent or empty, Sentry is not initialized and no data is sent.

---

## TelemetryDeck analytics

TelemetryDeck is already wired up via SPM. Set the App ID:

- Environment variable: `WORLD_CUP_BAR_TELEMETRYDECK_APP_ID`
- Or embed it directly in `MonitoringConfiguration.fromEnvironment()` for the production build.

Users can disable analytics at any time from **Settings → Analytics**.

---

## Better Stack uptime monitoring

Better Stack provides external HTTP uptime checks so API outages are visible even when no user has the app open.

### Setup

1. Log in to [betterstack.com](https://betterstack.com) → **Uptime** → **New monitor**.
2. Configure:
   - **URL:** `https://worldcup26.ir/get/games`
   - **Check interval:** 5 minutes
   - **HTTP method:** GET
   - **Expected status:** 200
   - **Timeout:** 15 seconds
3. Set up an alert channel (email or Slack) so you are paged if the API goes down for more than 10 minutes.
4. Optionally add a second monitor for `https://worldcup26.ir/get/teams`.

### Why it matters

If the worldcup26.ir API goes down, every user's app will show "Live data unavailable". Better Stack will alert you before user complaints arrive.

---

## App Store Connect checklist

- [ ] Bundle ID registered: `com.michilotl.WorldCupBar`
- [ ] App created in App Store Connect
- [ ] Pricing set (one-time paid, no subscription)
- [ ] Age rating configured
- [ ] Privacy policy URL set to `https://michilotl.com/apps/world-cup-bar/privacy/`
- [ ] Support URL set to `https://michilotl.com/apps/world-cup-bar/support/`
- [ ] EULA: use Apple's standard EULA (no custom EULA required)
- [ ] Screenshots captured (macOS, at least one size)
- [ ] Archive built with release signing
- [ ] TestFlight build validated before submission
