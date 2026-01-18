# Getting Started with the Basic Solution

The basic solution demonstrates the concepts of time series data visualization with Power BI and KQL databases using a publicly-available KQL database. More importantly, it can be easily customized to work with your data.

## Recommended Skills

| Skill Area | Level |
|------------|-------|
| KQL | :material-star: Basic |
| Power BI - Power Query | :material-star: Basic |
| Power BI - Reporting | :material-star: Basic |

## Prerequisites

- [x] Power BI Desktop installed
- [x] Access to a KQL database (Microsoft Fabric or Azure Data Explorer)
- [x] Access to a Fabric Workspace (to publish and share your report)

!!! note "Sample Data"
    This solution uses a publicly-accessible KQL database with sample data. You will need your own KQL database to work with your own data.

## Try the Basic Solution

Follow these steps to get started quickly:

1. **[Download or clone this GitHub repository](https://github.com/slavatrofimov/Time-Series-Visualization-with-Microsoft-Fabric)** to your local computer

2. **Open the project file** in Power BI Desktop:
   ```
   src/Time Series Viz - Basic/Time Series Viz - Basic.pbip
   ```

3. **Provide credentials** for your Microsoft account to sign into the publicly-available Azure Data Explorer cluster:
   ```
   https://help.kusto.windows.net/
   ```

4. **Start exploring** — drag the brush in the time series brush slicer to select time ranges and watch the report update

5. Optionally, **publish the report to your Fabric workspace** to share with others

---

## Adapt Basic Solution to Work With Your Data

### Step 1: Open the Project

1. [Download or clone this GitHub repository](https://github.com/slavatrofimov/Time-Series-Visualization-with-Microsoft-Fabric) to your local computer
2. Open the `Time Series Viz - Basic.pbip` file in Power BI Desktop

![Initial Power BI Report](../assets/Customize%20PBI%20Project/Initial%20Report.png)

### Step 2: Open Power Query Editor

Click on the **Transform Data** button to open the Power Query window:

![Click the Transform Data button](../assets/Customize%20PBI%20Project/Transform%20Data.png)

### Step 3: Manage Parameters

Click the **Manage Parameters** button:

![Start managing parameters](../assets/Customize%20PBI%20Project/Manage%20Parameters.png)

### Step 4: Configure Parameters

Update the following four parameters:

![Update parameter values](../assets/Customize%20PBI%20Project/Configure%20Parameters.png)

#### p_kql_cluster

Update with the URL of your KQL cluster, such as:

```
https://help.kusto.windows.net/
```
or
```
https://my-cluster-name.zX.kusto.fabric.microsoft.com
```

#### p_kql_db

Update with the name of your KQL Database.

#### p_kql_query_tag_metadata

Update with the base KQL query that will return tag metadata. The query will need to be adapted to the schema of your KQL database.

!!! warning "Required Columns"
    This query **must return the following 6 columns**, whose names must match exactly:

    | Column | Description |
    |--------|-------------|
    | `Tag` | Id of a tag or time series. **Must be unique!** |
    | `TagName` | User-friendly name of a tag. **Must be unique!** |
    | `Level1` | Top level of your tag hierarchy |
    | `Level2` | Second level of your tag hierarchy |
    | `Level3` | Third level of your tag hierarchy |
    | `Level4` | Fourth level of your tag hierarchy |

**Example query:**

```kql
TimeseriesHierarchy 
| project 
    Tag = TimeseriesId, 
    TagName = DisplayName, 
    Level1 = tostring(Path[0]), 
    Level2 = tostring(Path[1]), 
    Level3 = tostring(Path[2]), 
    Level4 = tostring(Path[3])
```

!!! tip "Validate First"
    Please verify that the query is valid before pasting it here!

#### p_kql_query_timeseries

Update with the base KQL query that will return your time series data.

!!! warning "Required Columns"
    This query **must return the following 3 columns**, whose names must match exactly:

    | Column | Description |
    |--------|-------------|
    | `Tag` | Id of the tag (corresponds to `Tag` in tag metadata) |
    | `Timestamp` | Date and time of each event |
    | `Value` | Numeric value for each observation |

**Example query:**

```kql
Timeseries 
| project 
    Tag = TimeseriesId, 
    Timestamp = Timestamp, 
    Value = Value
```

### Step 5: Authenticate

Provide credentials and sign into the KQL database specified by your parameters:

![Provide credentials and sign in](../assets/Customize%20PBI%20Project/Edit%20Credentials.png)

### Step 6: Configure Filters and Slicers

Update default filter and slicer settings to match your data.

![Update filters and slicers](../assets/Customize%20PBI%20Project/Set%20Filters%20and%20Slicers.png)

!!! important "Custom Anchor Date"
    The sample report specifies a *Custom Anchor Date* for relative date filtering. This should be either **cleared** or **updated** to match your data.

### Step 7: Explore and Publish

1. **Start exploring** — drag the brush to select time ranges and watch the report update
2. **Publish the report to your Fabric workspace** to share with others

---

## Next Steps

- Learn about the [Advanced Solution](advanced-solution.md) for more capabilities
- Explore [Configuration Options](../reference/configuration-options.md)
- Understand the [Architecture](../reference/architecture.md)
