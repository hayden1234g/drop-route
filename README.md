# Drop Route

Phone-friendly route planner for batched delivery orders. Live at https://hayden1234g.github.io/drop-route/

1. Enter your store address (or tap 📍 Here).
2. Add order screenshots (long scrolling screenshots are fine). Text is read on-device with Tesseract.js, and addresses plus delivery windows are pulled out. Edit anything it gets wrong.
3. **Find fastest route** tries every stop order (up to 9 stops; larger batches use a fast heuristic) and picks the one that finishes soonest while respecting delivery windows. Each minute late counts 5x.
4. Tap **Delivered** at each stop and the rest re-plan from there with fresh drive times.

Drive times come from free OSRM (typical speeds, no traffic) unless you paste a Mapbox public token (`pk.…`) in Settings, which gives live traffic for up to 9 stops.

Single static `index.html`, with no backend. Local preview: launch.json entry `drop-route` (port 4816).
