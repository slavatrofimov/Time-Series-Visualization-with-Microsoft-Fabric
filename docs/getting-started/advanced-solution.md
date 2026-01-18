# Getting Started with the Advanced Solution

The Advanced solution builds upon the foundation of the Basic solution, while enhancing it in several ways:

- :material-chart-timeline-variant: Demonstrates the use of **timeline markers** to show important events
- :material-tune-vertical: Demonstrates a **richer set of chart configuration options** when paired with suitably-rich tag metadata
- :material-code-braces: Demonstrates the ability to construct **more advanced KQL queries** to adapt the solution to unique schemas and requirements

## Recommended Skills

| Skill Area | Level |
|------------|-------|
| KQL | :material-star::material-star::material-star: Advanced |
| Power BI - Power Query | :material-star::material-star::material-star: Advanced |
| Power BI - Reporting | :material-star::material-star::material-star: Advanced |

## Prerequisites

- [x] Power BI Desktop installed
- [x] Access to the Power BI service
- [x] Access to a KQL Database (Microsoft Fabric or Azure Data Explorer)

!!! info "Sample Database"
    This sample solution uses the publicly-accessible KQL Database with sample data:
    
    - **Cluster:** `https://help.kusto.windows.net/`
    - **Database:** `Trender`

## Try the Advanced Solution

Follow these steps to get started quickly:

1. **[Download or clone this GitHub repository](https://github.com/slavatrofimov/Time-Series-Visualization-with-Microsoft-Fabric)** to your local computer

2. **Open the project file** in Power BI Desktop:
   ```
   src/Time Series Viz - Advanced/Time Series Viz - Advanced.pbip
   ```

3. **Provide credentials** for your Microsoft account to sign into the publicly-available Azure Data Explorer cluster:
   ```
   https://help.kusto.windows.net/
   ```

4. **Start exploring** — drag the brush to select time ranges and watch the report update

5. **Publish the report** to your Fabric workspace to share with others

---

## Adapt Advanced Solution to Work With Your Data

### Step 1: Open the Project

1. [Download or clone this GitHub repository](https://github.com/slavatrofimov/Time-Series-Visualization-with-Microsoft-Fabric) to your local computer
2. Open the `Time Series Viz - Advanced.pbip` file in Power BI Desktop

### Step 2: Open Power Query Editor

1. Click on the **Transform Data** button to open the Power Query window
2. Click the **Manage Parameters** button

### Step 3: Update Connection Parameters

Update the following two parameters:

| Parameter | Description | Example |
|-----------|-------------|---------|
| `p_kql_cluster` | URL of your KQL cluster | `https://help.kusto.windows.net/` or `https://my-cluster-name.zX.kusto.fabric.microsoft.com` |
| `p_kql_db` | Name of your KQL database | `Trender` |

### Step 4: Customize Queries

Update queries in the semantic model to modify the logic for generating KQL queries used to retrieve your time series data and relevant tag metadata.

!!! tip "Advanced Customization"
    The advanced solution provides flexibility for complex scenarios:
    
    - Custom KQL query generation logic
    - Multiple data source support
    - Advanced tag hierarchy handling
    - Timeline marker integration

### Step 5: Customize Report Visuals

Customize report visuals to show what matters most to you.

!!! warning "Expertise Required"
    Customizing the advanced solution requires high levels of proficiency with:
    
    - Power Query (M language)
    - KQL (Kusto Query Language)
    - Power BI visualization
    
    While the solution can be customized in a variety of ways, specific steps for adapting this solution to your needs are beyond the scope of this tutorial. Consider using the design of the sample solution as a **starting point** for your customization.

---

## Advanced Features

### Timeline Markers

The advanced solution supports timeline markers to highlight important events on your time series charts:

- Maintenance events
- Anomaly detections
- Shift changes
- Production milestones

### Enhanced Chart Configuration

More granular control over chart layouts:

- Multiple independent Y-axes
- Color coding by tag categories
- Small multiples configuration
- Legend customization

### Complex Query Generation

The Power Query layer can dynamically generate sophisticated KQL queries based on:

- User-selected tags
- Time range selections
- Aggregation preferences
- Filter configurations

---

## Next Steps

- Review the [Architecture](../reference/architecture.md) documentation
- Explore [Configuration Options](../reference/configuration-options.md)
- Learn about the [Time Series Brush Slicer](../reference/brush-slicer.md)
