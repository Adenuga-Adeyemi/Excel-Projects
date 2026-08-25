# Project Documentation

## Purpose

This project demonstrates how Microsoft Excel can turn regional demographic records into a navigable analytical story. Its central design choice is to separate the raw data layer, the Pivot Table aggregation layer, the calculation layer, and the presentation layer.

## Recommended Workbook Architecture

| Layer | Recommended worksheet | Responsibility |
| --- | --- | --- |
| Raw data | `Raw_Data` | Store the source extract without presentation formatting. |
| Clean table | `Clean_Data` | Standardize names, data types, missing values, and category labels. |
| Calculations | `Calculations` | Store percentages, ranks, dominant-category logic, and validation checks. |
| Pivot analysis | `Pivot_Tables` | Aggregate population by region and affiliation. |
| Dashboard | `Dashboard` | Present KPIs, filters, map, bars, and donut chart. |
| Notes | `Documentation` | Record source, refresh date, assumptions, and limitations. |

## Validation Checklist

Before publishing a refreshed workbook, confirm that the region list contains 16 unique regions, population columns are numeric, and each affiliation category is represented consistently. Check for duplicate rows, missing region names, negative values, and totals that do not reconcile to the selected source definition.

Then test the dashboard filter behavior for every region. Verify that the selected region is visible in the page heading or selector, the dominant-category label changes with the selection, charts update together, and zero values do not break the visual logic. Capture the refresh date and data source in the workbook notes.

## Suggested Derived Measures

| Measure | Example logic |
| --- | --- |
| Affiliation share | `Affiliation Population / Regional Total Population` |
| Dominant population | `MAX(Affiliation Population Range)` |
| Dominant affiliation | `INDEX(Affiliation Label Range, MATCH(Dominant Population, Affiliation Population Range, 0))` |
| Regional rank | Rank regional population in descending order. |
| Average regional population | Total population divided by the count of unique regions. |
| Regional variance | Document the exact variance definition used in the workbook. |

## Maintenance Notes

If a verified workbook is later added, place it in a clearly named folder such as `workbook/` and document its source, version, refresh date, and license. Do not overwrite the original source extract; retain a clean, reproducible transformation path. Update the README’s figures only after confirming that the values and category definitions match the new workbook.
