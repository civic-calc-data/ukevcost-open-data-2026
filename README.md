# UKEVCost Open Data (2026)

Open CSV datasets modelling the legislated UK electric company car BiK tax rise from 3% to 9% (2025/26 to 2029/30) across 15 EVs, 10,000-mile EV vs. petrol running costs including £200 VED road tax, and Octopus Agile half-hourly regional spreads across all 14 Great Britain DNO zones.

All figures are computed directly from HMRC BiK schedules, DVLA VED tables, the Ofgem Q4 2026 Price Cap, and Octopus Energy's public REST API. Interactive calculators and live tariff trackers live at [ukevcost.co.uk](https://ukevcost.co.uk/).

## Datasets in this repository

| File | Coverage | Live report & calculator |
|---|---|---|
| [`data/ev-bik-tax-jump-2025-2030.csv`](data/ev-bik-tax-jump-2025-2030.csv) | 15 popular UK EVs (£14,995 to £86,500 P11D): 20% and 40% BiK tax from 2025/26 (3%) to 2029/30 (9%), 5-year total, Employer Class 1A NI, and £50k+ ECS flag | [EV BiK Tax Jump Report](https://ukevcost.co.uk/reports/ev-bik-tax-jump-2025-2030/) / [BiK Calculator](https://ukevcost.co.uk/) |
| [`data/ev-vs-petrol-cost-per-mile-uk.csv`](data/ev-vs-petrol-cost-per-mile-uk.csv) | 8 charging & fuel profiles at 10,000 miles/year: pence/mile, energy cost, £200 Year 2+ VED, total annual cost, and saving vs. 45 MPG petrol | [EV vs Petrol Cost Report](https://ukevcost.co.uk/reports/ev-vs-petrol-cost-per-mile-uk/) / [EV Charging Calculator](https://ukevcost.co.uk/ev-charging-cost-calculator/) |
| [`data/octopus-agile-regional-spread-2026.csv`](data/octopus-agile-regional-spread-2026.csv) | All 14 GB DNO regions (1,440 half-hour slots each): mean, overnight (00–06), peak (16–19), best 4h window, min plunge, max peak, negative slots, and standing charge | [Octopus Agile Regional Spread Report](https://ukevcost.co.uk/reports/octopus-agile-regional-spread-2026/) / [Live Agile Tracker](https://ukevcost.co.uk/octopus-agile-prices/) |

---

## 1. EV Company Car BiK Tax Triples by 2029/30 (3% → 9%)

Under HMRC's legislated BiK schedule (3% in 2025/26, 4% in 2026/27, 5% in 2027/28, 7% in 2028/29, 9% in 2029/30), every UK EV company car driver sees annual BiK tax triple over four tax years:

| EV model | P11D | 40% BiK 2025/26 (3%) | 40% BiK 2026/27 (4%) | 40% BiK 2029/30 (9%) | 5-yr 40% total | Employer Class 1A (5 yr) | Over £50k ECS |
|---|---:|---:|---:|---:|---:|---:|:---:|
| MG4 EV SE Long Range | £29,495 | £353.94 | £471.92 | £1,061.82 | £3,303.44 | £1,238.79 | No |
| Tesla Model 3 RWD | £39,990 | £479.88 | £639.84 | £1,439.64 | £4,478.88 | £1,679.60 | No |
| Tesla Model Y LR RWD | £44,990 | £539.88 | £719.84 | £1,619.64 | £5,038.88 | £1,889.60 | No |
| BMW i4 eDrive40 M Sport | £57,890 | £694.68 | £926.24 | £2,084.04 | £6,483.68 | £2,431.40 | Yes |
| Porsche Taycan | £86,500 | £1,038.00 | £1,384.00 | £3,114.00 | £9,688.00 | £3,633.00 | Yes |

---

## 2. EV vs. Petrol Cost per Mile + £200 VED (10,000 Miles/Year)

Key findings from [`data/ev-vs-petrol-cost-per-mile-uk.csv`](data/ev-vs-petrol-cost-per-mile-uk.csv):
- **Home off-peak (Intelligent Octopus Go, 7p/kWh):** **2.20p/mile** (£420/yr incl. £200 VED), saving **£1,417/yr** vs. a 45 MPG petrol car (16.37p/mile, £1,837/yr).
- **Ofgem Q4 2026 Price Cap (26.32p/kWh):** **8.27p/mile** (£1,027/yr), still saving **£810/yr**.
- **Public AC kerbside (54p/kWh):** **16.97p/mile** (£1,897/yr) — **£60/yr more expensive** than petrol.
- **Public rapid DC only (79p/kWh):** **23.70p/mile** (£2,570/yr) — **£733/yr more expensive** than petrol.

---

## 3. Octopus Agile Regional Spread (14 GB DNO Regions)

Across 1,440 half-hourly Agile slots per DNO region:
- **Cheapest region — London (DNO C):** 35.32p/kWh mean, 26.75p/kWh best 4h daily window, 37.65p/day standing charge.
- **Most expensive region — Northern Scotland (DNO P):** 42.72p/kWh mean (+7.40p/kWh above London), 65.69p/kWh peak (16:00–19:00), -8.14p/kWh deepest plunge.
- All 14 GB regions recorded **31 to 32 negative-price half-hour slots** in the period.

---

## Primary Official Sources

- HMRC: [Company car BiK appropriate percentages](https://www.gov.uk/guidance/company-car-benefit-the-appropriate-percentage-480-appendix-2) and [2028/29–2029/30 BiK rate changes](https://www.gov.uk/government/publications/changes-to-company-car-tax-rates-for-the-tax-years-2028-to-2029-and-2029-to-2030)
- DVLA: [Vehicle tax rate tables (VED & ECS)](https://www.gov.uk/vehicle-tax-rate-tables)
- Ofgem: [Energy Price Cap](https://www.ofgem.gov.uk/energy-price-cap)
- Octopus Energy: [Public Products & Tariffs REST API](https://api.octopus.energy/v1/products/?brand=OCTOPUS_ENERGY&is_variable=true)

## Interactive Calculators and Embeds

- Company Car BiK calculator (2025–2030): https://ukevcost.co.uk/
- EV Salary Sacrifice calculator: https://ukevcost.co.uk/ev-salary-sacrifice/
- EV charging cost vs. petrol calculator: https://ukevcost.co.uk/ev-charging-cost-calculator/
- Live Octopus Agile & Tracker prices: https://ukevcost.co.uk/octopus-agile-prices/
- Lightweight iframe embeds (no sign-up): `https://ukevcost.co.uk/embed/bik/`, `https://ukevcost.co.uk/embed/ev-charging/`

## License and Citation

Licensed under [CC-BY-4.0](LICENSE). Citation metadata is in [`CITATION.cff`](CITATION.cff).

```text
UKEVCost (2026). UKEVCost Open Data 2026: UK EV BiK Tax Schedule (2025-2030), EV vs Petrol Cost per Mile, and Octopus Agile Regional Spread [Dataset]. https://ukevcost.co.uk/reports/ (CC-BY-4.0).
```
