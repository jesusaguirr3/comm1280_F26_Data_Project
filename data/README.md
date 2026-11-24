# Data

The notebook `../data_analysis/01_collect_permit_data.ipynb` downloads all the original data in this folder. We have not manually entered or edited any of the records.

## raw/

This folder contains three files in their original form, exactly as we received them from the city.

**`new_construction_building_permits_2016_2024.csv`** contains 9,486 rows, each representing a new construction building permit that Philadelphia issued between 2016 and 2024. It includes residential and commercial building permits only and serves as the foundation of our analysis.

**`all_permits_by_year_2016_2024.csv`** contains nine rows comparing the total number of permits the city issued each year with the number classified as new construction. Notebook 02 uses this file to distinguish changes in construction activity from changes in recordkeeping.

**`permit_record_system_by_month_2016_2024.csv`** groups monthly permits by the computer system that recorded them. This file helped us pinpoint when Philadelphia completed its transition between permit systems.

All three files come from the City of Philadelphia's Department of Licenses and Inspections through OpenDataPhilly. We downloaded them from the public SQL endpoint at https://phl.carto.com/api/v2/sql on November 24, 2026.

## Why we only count building permits

A single house can generate a small mountain of paperwork. In addition to a building permit, a construction project may require separate permits for electrical work, plumbing, heating and fire sprinklers. Counting every permit could mean counting the same house four or five times, with more complicated projects carrying greater weight in our analysis.

We therefore keep only Residential Building Permit and Commercial Building Permit records. This gives us a closer approximation of individual construction projects without inflating our counts with additional trade permits.

## The columns that matter

| Column | What we use it for |
|---|---|
| `permitissuedate` | Identifies when the city issued the permit and whether it met the tax deadline. |
| `permitdescription` | Distinguishes residential permits from commercial permits. |
| `typeofwork` | Allows us to filter for New Construction. |
| `opa_account_num` | Links permit records to property assessments. |
| `censustract` | Connects permit records to Census data. |

The dataset also contains information we have not yet incorporated into our analysis, including property addresses, scopes of work and council districts.

## cleaned/

The file `monthly_new_construction_2020_2024.csv` contains 57 rows, covering every month from April 2020 through December 2024. Each row contains the monthly residential and commercial building permit counts. Notebook 03 produces this file.

We deliberately start in April 2020 rather than 2016 because Philadelphia changed its permit records system during that period. The older records use different classifications, making direct comparisons unreliable. Notebook 02 explains how we identified this problem and selected our starting date.
