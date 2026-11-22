# Drop Route

Phone-friendly route planner for batched delivery orders. Live at https://hayden1234g.github.io/drop-route/

1. Enter your store address (or tap 📍 Here).
2. Add order screenshots (long scrolling screenshots are fine). Text is read on-device with Tesseract.js, and addresses plus delivery windows are pulled out. Edit anything it gets wrong.
3. **Find fastest route** tries every stop order (up to 9 stops; larger batches use a fast heuristic) and picks the one that finishes soonest while respecting delivery windows. Each minute late counts 5x.
4. Tap **Delivered** at each stop and the rest re-plan from there with fresh drive times.

**Tips tab:** each delivered stop is logged with the customer name read from the screenshot. Add pay and tip later. It shows average tip by ZIP (map), by store and by repeat customer, and flags repeat customers on new orders. Each order has tappable options (Replaced item, Tip was a %, Always does 20%, Left a note, etc., editable), and "Tips by option" compares average tips with and without each one. The log lives in the browser; connect a Google Sheet (Apps Script web app, the script is generated on the Tips tab with a per-device secret key) for automatic backup and restore, or use Export CSV.

Drive times come from free OSRM (typical speeds, no traffic) unless you paste a Mapbox public token (`pk.…`) in Settings, which gives live traffic for up to 9 stops.

Single static `index.html`, with no backend. Local preview: launch.json entry `drop-route` (port 4816).
