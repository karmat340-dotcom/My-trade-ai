# TradeMind AI Professional — Android-ready starter (v4.0)

This package preserves the existing TradeMind AI v3.7.4 dashboard and adds an installable PWA shell, offline app-shell caching, app icons, Capacitor configuration, and a GitHub Actions workflow that builds a debug APK in the cloud.

## What is included
- Existing market dashboard: candlesticks, Binance public market data, indicators, scanner/watchlist/journal and trade-plan tools from the supplied v3.7.4 HTML.
- PWA manifest, service worker, theme metadata and app icons.
- Capacitor Android project configuration.
- GitHub Actions workflow to produce a debug APK artifact.

## Important limitations — not yet a complete production trading service
- The APK workflow has not been run from this chat; the generated APK is not included.
- This package does not yet connect a personal Binance account. It uses public market data only.
- Portfolio balances, private positions, order history, cloud login/sync, push notifications and AI-hosted analysis require backend deployment and additional implementation.
- No trade execution endpoint is included. The intended design is read-only account access first, with every trade remaining a manual user decision.
- The HTML source passed JavaScript syntax checks, but a full live-browser/device test has not been completed. Third-party chart library and Binance network access are required for live features.

## Build the APK using only an Android phone
1. Create a GitHub repository and upload the contents of this folder (keep the `.github/workflows` folder).
2. Open the repository's **Actions** tab in your phone browser.
3. Select **Build TradeMind Android APK** → **Run workflow**.
4. When it finishes successfully, open the run and download the `TradeMind-AI-debug-apk` artifact.
5. Extract the ZIP and install `app-debug.apk` on your Android phone. Android may ask you to allow installs from your browser/files app.

A GitHub account and successful cloud build are required. This debug APK is for testing, not a Play Store release.

## Install as a website app first
Host the `public` folder on an HTTPS static host. Open the site in Chrome on Android and use **Install app** / **Add to Home screen**. Offline caching covers the app shell only; live market data still needs internet.

## Security
Never put Binance API secrets in the HTML, GitHub repository, or chat. For a future account integration, create a dedicated API key with read-only permissions and no withdrawals or trading, store secrets only as server-side environment variables, and verify the key permissions before connecting.
