# Data analysis

This folder contains four notebooks that run in numerical order. Notebook 01 handles the data collection, so anyone can reproduce our analysis from a fresh clone with pandas, matplotlib and requests.

## The notebooks

**`01_collect_permit_data.ipynb`**

This notebook retrieves Philadelphia's permit records from the city's public SQL endpoint and saves them to `data/raw/`. It also explains how we filter the data. Since individual construction projects often generate several permits, we exclude separate electrical, plumbing and sprinkler permits to avoid counting the same project multiple times.

**`02_data_quality_and_coverage.ipynb`**

This notebook examines the reliability of the older permit records. At first glance, Philadelphia appeared to experience an extraordinary construction boom between 2016 and 2019, with new construction permits increasing more than thirtyfold while overall permit activity remained relatively stable.

Digging into the records revealed that Philadelphia had changed its permit systems. This discovery changed the course of our project. Had we taken the original numbers at face value, we would have reported a dramatic policy effect that largely reflected a change in recordkeeping. The notebook establishes April 2020 as the earliest reliable starting point for our analysis.

**`03_the_deadline_effect.ipynb`**

This notebook contains our main analysis. It organizes permits by month, measures the December 2021 surge and examines whether developers simply moved future projects ahead of schedule or whether permitting activity experienced a more sustained decline. It also explains why commercial construction did not work as a comparison group.

**`04_assessments_and_neighborhoods.ipynb`**

This notebook remains in progress. We want to examine whether property values influenced how developers responded to the deadline. Since developers stood to save more in property taxes on expensive buildings, we expect a stronger response in areas with higher property values if the abatement drove the rush. The data collection queries currently run, but we have not yet completed the analysis.

## The numbers notebook 03 produces

| Measure | Permit count |
|---|---:|
| Monthly average, January to October 2021 | 98 |
| November 2021 | 218 |
| December 2021 | 642 |
| January 2022 | 36 |
| Annual pace before the deadline | About 1,177 |
| Annual pace, 2022 to 2024 | About 628 |
| Estimated permits pulled forward during the rush | About 664 |
| Cumulative shortfall relative to the old pace | About 1,649 |

## How we split the work

We divide the notebooks between ourselves to avoid stepping on each other's toes. Since `.ipynb` files can be difficult to merge, each notebook has one owner and only that person edits it.

We pull the latest changes before starting work, push our changes when we finish and keep each other informed so that neither of us works from an outdated version of the repository.
