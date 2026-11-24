# What happens when a tax break ends?

Philadelphia's ten-year abatement and the December 2021 deadline.

COMM 1280, Data Science for Communication, Fall 2026. Jesus Aguirre and Lisandro Collazo.

## The question

For nearly twenty years, Philadelphia offered developers a generous deal: build a home and pay no property tax on the new building for ten years. City Council eventually reduced the abatement and introduced a 1% tax on residential construction. Both changes took effect on January 1, 2022, giving developers until December 31, 2021, to secure their building permits under the old deal.

We wanted to see how developers responded. Did they race against the clock to secure their permits, and did construction activity return to normal once the deadline passed?

## What we found

Between January and October 2021, Philadelphia issued an average of 98 permits for new residential construction each month. That number jumped to 642 in December before dropping to 36 in January 2022.

We estimate that developers pulled roughly 664 permits forward during the rush. However, the city issued approximately 1,649 fewer permits between 2022 and 2024 than its previous pace would suggest. The rush accounts for only about 40% of that shortfall, suggesting that more than a simple change in timing occurred.

Interest rates also climbed throughout 2022, making construction more expensive to finance. Until we separate the effects of rising interest rates from those of the tax changes, we cannot attribute the entire decline to the deadline.

## Two discoveries that shaped our project

**The records told a misleading story.** Our initial analysis showed new construction permits climbing from 326 in 2016 to 10,281 in 2019. A thirtyfold increase certainly caught our attention, especially since the city consistently issued between 44,000 and 64,000 total permits each year during that period. Philadelphia had switched permit records systems, and the older records classified construction differently. We traced the transition to March 2020 and began our analysis in April 2020. Notebook 02 walks through this discovery.

**Our comparison group fell apart.** We originally planned to compare residential construction with commercial construction, assuming the new policy left commercial properties untouched. However, a separate ordinance reduced the commercial abatement on the same date, and commercial permits experienced a similar spike, increasing by a factor of 5.6. Finding a comparison group that neither ordinance affected remains our biggest challenge.

## Getting around the repository

- `data/` contains the original downloads and cleaned monthly permit counts.
- `data_analysis/` contains four notebooks, numbered in the order they should run. Notebook 01 downloads the necessary data, allowing anyone to reproduce our analysis from a fresh clone.
- `data_story/` contains our written piece for a general audience.
- `presentations/` contains our presentation slides as PDFs.

Notebooks 01 through 03 are complete. Notebook 04 is still in progress.

## Where the data comes from

We collected building permits and property assessments from the City of Philadelphia through OpenDataPhilly, using the city's public SQL endpoint. Neighborhood income data comes from the Census Bureau's American Community Survey.

We reviewed Philadelphia City Council bills 200366 and 200653 to understand the policy changes. Guidance from the Philadelphia Water Department, published in December 2021, clarified the requirement to secure an issued building permit by the deadline.

Full APA citations appear on the references slide of our presentation.
