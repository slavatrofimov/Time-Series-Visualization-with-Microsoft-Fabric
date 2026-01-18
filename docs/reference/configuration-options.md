# Configuration Options

Users can control the analysis experience through report filters and slicers. This page documents all available configuration options.

## Time Range Settings

### Initial Time Range

Users can specify the initial time range using the **Show data for the last** slicer with relative periods:

| Option | Description |
|--------|-------------|
| 1 min | Last 1 minute |
| 5 min | Last 5 minutes |
| 15 min | Last 15 minutes |
| 1 hour | Last 1 hour |
| 6 hours | Last 6 hours |
| 1 day | Last 24 hours |
| 7 days | Last 7 days |
| 30 days | Last 30 days |
| Custom | Specify arbitrary start and end dates |

### Custom Anchor Date

!!! tip "Historical Analysis"
    Use the **Custom Anchor Date** filter to streamline analysis of historical data preceding a specific date. When set, relative time periods are calculated from the anchor date rather than the current time.

### Custom Date Range

When selecting *custom* from the **Show data for the last** slicer, you can specify:

- **Start date**: Beginning of the analysis period
- **End date**: End of the analysis period

### Time Series Brush Range

The time series brush slicer provides a high-level overview of the initial time range. By dragging the handles, you can:

- Zero-in on a specific portion of the time range
- Expand or contract the selected window
- Pan across the time range

## Aggregation Settings

### Max Bin Count

Controls the maximum number of bins into which the selected time range should be split.

| Setting | Effect |
|---------|--------|
| Lower values (e.g., 100) | Smoother charts, easier to interpret trends |
| Higher values (e.g., 1500) | More detailed and granular charts |

!!! note "Performance Balance"
    This setting balances detail with performance and readability while helping to satisfy [Power BI's data point limits](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-data-points)

### Preferred Time Grain

Specify the preferred time granularity for analysis:

| Option | Description |
|--------|-------------|
| Auto | Intelligently determines granularity based on time period and Max Bin Count |
| 1 sec | 1-second intervals |
| 1 min | 1-minute intervals |
| 5 min | 5-minute intervals |
| 15 min | 15-minute intervals |
| 1 hour | 1-hour intervals |
| 1 day | Daily intervals |
| 7 days | Weekly intervals |

!!! warning "Time Grain Behavior"
    This setting is treated as a **suggestion**. If the specified grain would result in more time bins than permitted by the *Max Bin Count* setting, the report will behave similarly to the *Auto* setting.

### Aggregation Method

Select how to summarize raw data points within each time bin:

| Method | Use Case |
|--------|----------|
| `avg` | General trend analysis |
| `sum` | Cumulative metrics (e.g., production counts) |
| `min` | Finding minimum values or dips |
| `max` | Finding peak values |
| `count` | Event frequency analysis |
| `count_distinct` | Unique value counting |

## Chart Configuration

### Layout Options

Control how the main line chart displays multiple time series. This configuration allows you to control:

- Whether each time series (or tag) is split into a **separate chart** with an independent vertical axis
- Whether each time series is differentiated by **color**

## Tag Selection

### Tag Hierarchy

Use the hierarchical slicer to navigate through tag levels:

```
Level 1 (e.g., Plant)
└── Level 2 (e.g., Area)
    └── Level 3 (e.g., Unit)
        └── Level 4 (e.g., Instrument)
```

This helps users find the right tags for analysis in large tag databases.

### Tags

After filtering with the hierarchy, select one or more tags to include in detailed analysis.

!!! tip "Multi-Tag Analysis"
    When selecting multiple tags, use the Chart Configuration options to optimize how they're displayed together.

## Statistics

### Toggle Statistics Tab

Activate the **Statistics** tab to display:

| Statistic | Description |
|-----------|-------------|
| **Descriptive Statistics** | Mean, median, standard deviation, min, max for each tag |
| **Correlation Coefficients** | Pearson correlation between tags (when analyzing multiple tags) |
