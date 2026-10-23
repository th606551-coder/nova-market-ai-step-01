# NOVA MARKET AI — Step 1 UI Prototype

This build recreates the screenshot's dark trading layout, neon cyan scanner, floating robot, right-side panel, tabs, draggable controls, minimize/restore, and animated scan sequence.

## Files
- `index.html` — interface markup
- `style.css` — responsive visual design and scan effects
- `app.js` — interactions, drag controls, demo history, scan animation
- `scanner-engine.js` — EMA/RSI helper for valid supplied OHLC candles
- `bookmark.js` — bookmark loader template (replace the Netlify base URL)

## Run locally
Open `index.html` in a modern browser or deploy all five files to Netlify as a static site.

## Netlify deployment
1. Extract this ZIP.
2. Open Netlify and create a new site by manual deploy / drag-and-drop.
3. Upload the folder contents so `index.html` is at the site root.
4. Copy your published Netlify URL.
5. Open `bookmark.js`, replace `https://YOUR-NETLIFY-SITE.netlify.app/` with your exact site URL, and copy the one-line `javascript:` bookmarklet into a browser bookmark URL field.

## Important limitations
- The chart candles and scan animation are illustrative demo visuals, not live Quotex data.
- The current scan intentionally returns `WAIT` because no verified live candle feed is connected.
- Quotex may render chart data in a protected canvas and may block third-party scripts. This loader cannot guarantee access to the chart or survive navigation to other pages/apps.
- Auto Repeat repeats the demo scan at 30-second intervals only when enabled in Settings. It does not create real-time data.
- No automatic trading or trade-button clicking is implemented.
- Do not place private API keys in frontend code.

## Next implementation step
Connect a legitimate, documented candle-data adapter, validate timestamps and OHLC values, then pass the verified candles into `NovaScanner.analyze(candles, threshold)`. Keep data source and timestamps visible in results.
