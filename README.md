# Management Fee Calculator

A small, single-page web app that calculates a tiered (breakpoint) management fee given assets under management (AUM).

## Features

- Editable rate tiers (add/remove breakpoints, adjust each tier's threshold and rate)
- Annual, quarterly, or monthly fee output
- Live per-tier breakdown showing exactly how much of the AUM falls into each band
- Effective blended rate
- Runs entirely client-side in the browser — no server, no data leaves the page

## Running it

No build step or dependencies. Just open `index.html` in any browser:

```
# Windows
start index.html

# macOS
open index.html
```

Or, in VS Code, install the "Live Server" extension and click "Go Live" for auto-reload while editing.

## How the calculation works

Fees are computed using a standard breakpoint schedule: each tier's rate applies only to the portion of AUM that falls within that tier, not the whole balance. For example, with tiers of 1.00% up to $1M and 0.75% above that, an account with $2M pays 1.00% × $1,000,000 + 0.75% × $1,000,000, not 0.75% on the full $2M.

## Ideas for extending this

- Add a "compare two fee schedules side by side" mode
- Export the breakdown as CSV or PDF
- Support minimum fee floors or fee caps
- Save/load named fee schedules
