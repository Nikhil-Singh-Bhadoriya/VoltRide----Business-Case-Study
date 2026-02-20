# Charging Stations EDA Summary

## Dataset
- Source: Charging_Stations.csv (40 records, 5 columns)
- Columns: Station_ID, City, Zone (1–10), Chargers_Available, Avg_Wait_Time_Min

## Key Findings
- Coverage: 40 stations across 4 cities — Delhi (12), Hyderabad (12), Bengaluru (10), Mumbai (6).
- Chargers availability: mean 4.3, median 4, IQR 3–5.5, min 2, max 7.
- Wait times: mean 20.1 min, median 20 min, IQR 13–28, min 5, max 34.
- By city (avg wait • total chargers): Delhi 19.1 min • 52; Hyderabad 19.3 min • 49; Bengaluru 20.4 min • 45; Mumbai 23.3 min • 27.
- Zones with most stations: Zones 1 and 7 (7 each) and Zone 8 (6). Sparse zones: 4, 5, 6, 10 (2 each) and Zone 2 (4).
- Correlation: Chargers vs wait time is very weak (≈ +0.11); simply adding chargers does not guarantee lower waits.
- Outliers: Waits above 30–34 min in specific pockets; chargers below 3 in a few Mumbai/Delhi zones.

## Detailed Insights (from notebook outputs)
- City distribution and performance: Delhi and Hyderabad host 60% of stations and deliver the lowest average waits (<20 min). Mumbai is the smallest network and also the slowest (23.3 min) with the lowest total capacity (27 chargers).
- Zone patterns: High coverage in Zones 1 and 7; low coverage in Zones 4–6 and 10. Several low-coverage zones still show mid-to-high waits, indicating demand-pressure pockets despite fewer stations.
- Best performers (lowest waits): Hyderabad Zone 3 (e.g., CS209 at 5 min) and Delhi Zones 1/3 (5–10 min range) combine moderate chargers with low waits.
- Worst performers (highest waits): Hyderabad Zone 6 (CS239 at 34 min), Delhi Zone 5 (CS230 at 32 min), Mumbai Zone 1 (CS228 at 31 min), Bengaluru Zone 7 (CS202/CS214 at 33 min). These are prime targets for interventions.
- City-zone contrasts: Bengaluru shows wide spread in waits across zones (7 vs 31–33 min), suggesting uneven deployment. Delhi shows both best and worst pockets, so intra-city balancing matters.
- Distribution shapes: Chargers are clustered around 3–6 units; waits are centered near 20 min with a right tail beyond 30 min (notably in the worst zones above).
- Multivariate read: Encoded City/Zone correlations with wait are near zero; Zone-by-City heatmaps highlight that wait performance is locality-specific rather than driven by overall city means.

## Opportunities
- Reduce waits in the identified hot spots: Hyderabad Zone 6, Delhi Zone 5, Mumbai Zone 1, Bengaluru Zone 7.
- Add or reallocate chargers to under-served zones with higher waits and low capacity: Zones 4–6 and 10.
- Protect strong performers: Keep scaling Delhi Zone 1/3 and Hyderabad Zone 3 where waits are already low to absorb future demand.
- Investigate local drivers: Because correlation is weak, collect/monitor demand peaks, dwell times, and routing constraints before adding hardware; consider queue management and scheduling.
- Balance within cities: Especially for Bengaluru and Delhi, shift incremental capacity toward their high-wait zones instead of adding evenly.
