# Global Operations Reporting & Automation System

Portfolio project demonstrating multi-region operational reporting, Power Query consolidation, KPI standardization, exception monitoring, and interactive Power BI reporting.

> **Portfolio note:** All operational records are simulated and were created for demonstration purposes.

## Project Summary

This project models a recurring global operations reporting process across **five regions** using standardized weekly source workbooks.

The workflow consolidates regional operating data into a refreshable master dataset and reports on throughput, SLA performance, backlog, errors, and processing efficiency.

Architecture:

**5 Regional Excel Inputs → Power Query → Consolidated Dataset → Validation Layer → Power BI**

## Source Model

The project uses standardized regional workbooks for:
- North America
- Europe
- Asia Pacific
- Latin America
- Middle East

Across the five sources, the model contains **780 weekly operational records**.

Core fields include:
- Week start
- Region / region code
- Team
- Tasks received
- Tasks completed
- Backlog
- SLA-met count
- Errors
- Average completion hours

## Power Query Consolidation

Because the project was developed on macOS, Excel's Windows-only **From Folder** workflow was not available. Instead, each regional workbook was connected individually in Power Query and appended into a consolidated global query.

The final design still supports the real operating requirement: **new weekly records added to an existing regional workbook are incorporated automatically on refresh**.

The transformation layer also includes:
- data type standardization
- text cleaning
- source-file traceability
- completion validation
- SLA validation
- volume validation
- calculated completion, SLA, and error rates
- backlog and SLA performance flags
- overall data-quality status

## Validation

The consolidated model was tested by adding a new regional source row, refreshing the global workbook, and confirming that the record appeared automatically in the combined dataset.

A validation summary was created to reconcile regional task volumes, completed work, backlog, average completion hours, data-quality flags, SLA validation, and weekly trends.

## Power BI

Built a three-page interactive operations report:

1. **Global Overview** — total tasks, completion rate, SLA compliance, error rate, average backlog, average completion time, weekly work-volume trend, and regional comparison
2. **Regional Performance** — regional SLA compliance, error rate, backlog, completion time, and comparison table with conditional formatting
3. **Trends & Exceptions** — weekly SLA, error-rate, backlog and completion-time trends plus operational exception detail

## Key Portfolio Metrics

- **780** simulated weekly operating records
- **5** global regions
- **4** teams per region/week
- **3** interactive Power BI pages
- refreshable Power Query consolidation workflow

## Technology

`Excel` · `Power Query` · `Power BI` · `PowerPoint`

## Repository Structure

```text
├── data/
│   ├── Operations_Global_Consolidation.xlsx
│   └── regional-inputs/
├── screenshots/
│   ├── power-query.png
│   ├── global-overview.png
│   ├── regional-performance.png
│   └── trends-exceptions.png
└── README.md
```

## Skills Demonstrated

- Multi-source operational reporting
- Power Query transformation and append logic
- Refreshable reporting workflows
- Data validation and quality controls
- SLA, backlog, throughput, and error-rate analysis
- Power BI semantic modeling and DAX
- Management reporting and exception analysis

## Disclaimer

This is a **simulated portfolio project**. It does not contain confidential employer, client, or production operational data.
