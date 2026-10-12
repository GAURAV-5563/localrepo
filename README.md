# Localrepo

An interactive delivery-operations analytics dashboard built as a static website.

## Live dashboard

Open the [Delivery Operations Dashboard](https://gaurav-5563.github.io/localrepo/data-analytics-projects/delivery-dashboard.html).

## What it does

The dashboard reads the sample `delivery_data.csv` in the browser and calculates:

- Delivered revenue, cancellation rate, on-time rate, and average delivery time.
- Monthly delivered-revenue trends.
- Revenue, delivery quality, ratings, and cancellations by city, restaurant category, and acquisition channel.
- Data-derived highlights and downloadable segment summaries.

The data is synthetic, generated with a fixed seed for demonstration. It is not live business data.

## How to run locally

From the repository root:

```bash
cd data-analytics-projects
python -m http.server 8000
```

Open `http://localhost:8000/delivery-dashboard.html`. A local server is needed so the browser can fetch the CSV.

## How the project works

1. The reproducible generator in the [source analysis project](https://github.com/GAURAV-5563/data-analytics/tree/main/analytics_projects/delivery_operations) creates synthetic delivery orders.
2. The dashboard loads the CSV with PapaParse and computes its summaries and insights in the browser.
3. Tabs switch between city, cuisine, and channel views; the metric selector changes the comparison chart; the download button exports the selected segment.
4. GitHub Pages serves the static files from `main`; pushes to `main` trigger a Pages build.

The current dashboard uses CDN-hosted PapaParse and fonts, so visitors need internet access.

## Future improvements

- Add date-range and city filters.
- Support uploading a CSV and validate its columns before analysis.
- Connect a secure API or scheduled pipeline when real delivery data is available.
- Add weekday and peak-hour analysis, service-level targets, and trend alerts.