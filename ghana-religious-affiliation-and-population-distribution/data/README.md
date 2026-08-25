# Data Guide

The article describes a regional Ghana population dataset with religious affiliation counts. This folder is reserved for a verified source extract or workbook supplied by the project owner.

## Expected Schema

| Field | Type | Notes |
| --- | --- | --- |
| `Region` | Text | One of Ghana’s 16 administrative regions represented in the project. |
| `Total Population` | Integer | Regional population total. |
| `Pentecostal/Charismatic` | Integer | Population count for the category. |
| `Protestant` | Integer | Population count for the category. |
| `Islam` | Integer | Population count for the category. |
| `Catholic` | Integer | Population count for the category. |
| `Other Christian` | Integer | Population count for the category. |
| `Other Religion` | Integer | Population count for the category. |
| `No Religion` | Integer | Population count for the category. |
| `Traditionalist` | Integer | Population count for the category. |

## Provenance Requirements

When adding data, record the publisher, dataset title, URL, release or census year, download date, license, and any transformation steps. Preserve the original extract separately from cleaned or reshaped data.

The source article references official or census-aligned data. A public Ghana Statistical Service StatsBank table is linked in the project README as a starting point for source verification. The values shown in the article preview should not be treated as independently validated until reconciled to the exact source release and category definitions.

## Current Status

No `.xlsx`, `.csv`, or other source data file is included at present because the supplied article did not expose a downloadable workbook through the accessible page. This avoids presenting fabricated or unverifiable data as an original project artifact.
