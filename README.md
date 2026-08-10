# Space Tourism Price Dataset

Machine-readable datasets behind OuterSpaceTrip.com's
[Space Tourism Price Index](https://outerspacetrip.com/guides/space-tourism-price-index/) —
commercial human-spaceflight seat prices, operator status, and the passenger flight
log, compiled and re-verified on the live site and mirrored here weekly.

## Files

| File | What it holds |
|---|---|
| `space-tourism-prices.json` | Current seat price and operational status for every tracked operator (`operators[]`: price, flight length, altitude, training, launch site, status), the four price tiers (`tiers[]`: suborbital → orbital → lunar → Mars), and the historical price curve back to 2001 (`price_history[]`) |
| `space-tourism-flights.json` | The commercial passenger flight log (`flights[]`: date, mission, operator, type, milestone, per-row source label and URL) |

Both files are self-describing: top-level `name`, `description`, `publisher`,
`license`, and `attribution` fields (and, for prices, `last_verified`) travel with
the data.

## Provenance & freshness

- Compiled and maintained on [OuterSpaceTrip.com](https://outerspacetrip.com);
  every row carries its own source and date.
- The live site regenerates these files on every deploy, and prices are
  re-verified on a weekly cycle.
- This repository auto-refreshes weekly from the canonical live copies
  ([space-tourism-prices.json](https://outerspacetrip.com/space-tourism-prices.json) ·
  [space-tourism-flights.json](https://outerspacetrip.com/space-tourism-flights.json))
  via `.github/workflows/refresh.yml`. Human-readable dataset pages:
  [/price-dataset](https://outerspacetrip.com/price-dataset/) ·
  [/flight-log-dataset](https://outerspacetrip.com/flight-log-dataset/).

## License & attribution

**CC BY 4.0.** The license covers this compilation — its selection, arrangement,
verification dates, and annotations; the underlying prices and flight facts are
facts. Reuse freely with attribution:
**"OuterSpaceTrip.com Space Tourism Price Index"**, linked to
<https://outerspacetrip.com/guides/space-tourism-price-index/>.
See `LICENSE` and `CITATION.cff`.

## Scope (by design)

This repository contains the datasets, their license, and the refresh workflow —
nothing else, ever.

Questions or corrections: rob@outerspacetrip.com
