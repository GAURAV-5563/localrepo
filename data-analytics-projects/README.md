# data-analytics-projects
<br>
Author - Gaurav Bisht (gaurav)

## Interactive Projects

- [Delivery Operations Dashboard](./delivery-dashboard.html) — explore monthly revenue and compare cancellation rates, on-time performance, and customer ratings by city, restaurant category, or acquisition channel. Includes downloadable CSV summaries.

### Live dashboard

After GitHub Pages finishes its first deployment, open the [Delivery Operations Dashboard](https://gaurav-5563.github.io/localrepo/delivery-dashboard.html).

The dashboard is a static browser app. Serve it over HTTP so it can load its local CSV. Its figures come from the reproducible [delivery operations analysis](https://github.com/GAURAV-5563/data-analytics/tree/main/analytics_projects/delivery_operations); the data is synthetic.

### Run the interactive dashboard locally

The dashboard reads `delivery_data.csv` in the browser. Start a local server from the repository root so the browser can load the CSV:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000/delivery-dashboard.html`. Regenerate the sample dataset with `python analytics_projects/delivery_operations/generate_data.py`, then copy the updated CSV to the repository root to refresh the dashboard data.

## How the project works

1. `generate_data.py` creates a reproducible sample of 1,500 synthetic orders.
2. The dashboard loads `delivery_data.csv` in the browser and calculates totals, rates, monthly revenue, and segment summaries from its rows.
3. City, restaurant category, and acquisition-channel views can be compared across metrics; the selected segment can be exported as CSV.

The sample data is synthetic, not live business data. The dashboard currently needs internet access to load its CSV parser and fonts from CDNs.

## Future improvements

- Add date-range and city filters.
- Allow users to upload a CSV and validate its columns before analysis.
- Connect a secure API or scheduled data pipeline when real operational data becomes available.
- Add weekday and peak-hour analysis, service-level targets, and trend alerts.
