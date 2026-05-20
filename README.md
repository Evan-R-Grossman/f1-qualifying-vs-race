# f1-qualifying-vs-race
Separating driver skill from car performance across the F1 Hybrid Era (4,626 rows, 11 seasons, Excel + Tableau)

F1 Qualifying vs Race Performance — Hybrid Era (2014–2024)

## The Question

A driver's finishing position depends on two things: how fast their car is, and how well they race. Qualifying captures the first. Race-day position changes capture the second. This project separates those signals across the Hybrid Era of Formula 1 to answer: **who actually races well, and who is just driving a fast car?**

The 2014–2024 window is deliberate — it's the V6 turbo-hybrid era, a single regulation cycle, which keeps the cars comparable across seasons.

## The Data

- **4,626 driver-race rows** covering every driver at every race
- **59 drivers, 228 races, 11 seasons** (2014–2024)
- Per-driver, per-race grid position, finish position, points, and DNF status
- Joined from 7 source files (races, results, qualifying, drivers, constructors, status, circuits) from the Kaggle "Formula 1 World Championship 1950–2024" dataset (Ergast API)

## Methodology

- Joined 7 source CSVs on shared keys (driver_id, race_id, constructor_id) to build a master per-race table
- Computed positions gained/lost per race, then averaged across season and career
- Filtered to drivers with 30+ starts so the rankings reflect pattern, not single-race noise
- Cross-tabulated pole conversion by team to isolate car effects from driver effects
- Tableau for the polished visualization layer

## Key Findings

- **Race-day movement comes mostly from drivers who started farther back.** Pastor Maldonado led the dataset at +3.78 average positions gained per race (avg grid 14.76, avg finish 12.04). This isn't a "best driver" ranking — it reflects opportunity, since front-runners can't gain positions they don't have.
- **Pole conversion is mostly a team story.** Among teams with 5+ poles, Red Bull converted **73.9% (34/46) of poles into wins** — the highest in the dataset. Mercedes followed at 56%, Ferrari at just 26.1% despite having the same number of poles as Red Bull.
- **Circuits change the story.** Hockenheimring, Sepang, and Baku created the most race-day movement; Marina Bay and Interlagos showed the highest pole-to-win rates (75% and 70%) — suggesting some tracks reward qualifying far more than others.
- **2024 was the most competitive season of the era**, with **7 unique race winners** — the most in the 2014–2024 period.

## Why This Matters

The hard part of any performance analysis is separating what's driven by the system from what's driven by the individual. Same problem shows up plenty of other places — sales reps on different territories, students at different schools.

## Skills Demonstrated

- Multi-source data structuring across 4,600+ rows from 7 joined files
- Pivot table analysis with multiple groupings (driver, team, season, grid position, circuit)
- Identifying confounding variables (car vs driver effect) and reasoning about them in writing
- Visual storytelling in Tableau

## Files

- `F1_Qualifying_vs_Race_Portfolio_4Tab_Final.xlsx` — full dataset, dashboard, and analysis
- `tableau_dashboard.twbx` — interactive visualization (live version: [Tableau Public link])
- `README.md` — this file
