## Connection to BUSI2035

Source: https://github.com/anorakadrian/osint-investigator-dashboard

Companion: https://manus.im/app/BdZkLVDwGUmTAqT79yMbbN

For HKBU BUSI2035 this dashboard is opportunity recognition, not a finished venture. It turns a vague fintech idea into a geography-specific Business Model Canvas and a list of untested assumptions.

Observed public series: internet-user share, WGI RQ/RL/PV mean, listed-firm count + market cap. Those are screening factors, not TAM, Similarweb, or legal clearance. Canvas blocks are **hypothesis**.

# OSINT Investigator Dashboard

Single-file choropleth + deterministic BMC rule table. Live file: index.html. No API keys. Missing years stay No data.

## Live vs hypothesized

| Surface | Status | Source |
|---|---|---|
| Country polygons | Observed | Natural Earth via D3 GeoJSON |
| Digital attention | Observed percentile | WDI IT.NET.USER.ZS |
| Public-source climate | Observed percentile | WGI RQ, RL, PV |
| Listed-market depth | Observed weighted percentile | CM.MKT.LCAP.CD, CM.MKT.LDOM.NO |
| Nine BMC blocks | Hypothesis | Rule table on High/Mid/Low |

## Algorithms

1. Latest non-null join on mrv=8 World Bank rows per ISO-3. Drop aggregates.
2. Percentile `i / (n - 1) * 100`.
3. Climate = percentile(mean available WGI). Not a threat score.
4. Depth = 0.6 * percentile(log cap) + 0.4 * percentile(log firms).
5. Buckets at 33 and 67 select one of nine catalog propositions.

Does not do Similarweb, EDGAR, court records, PMF proof, or minute-level polling.
