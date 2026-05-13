# Surpac — Drillhole to Pit Design Workflow

This repository documents an end-to-end **Surpac** workflow that takes raw exploration drillhole data and develops it into a complete **open-pit mine design**. It includes a step-by-step tutorial PDF along with the underlying **Cu-Co drillhole dataset** used to build the tutorial, so that readers can replicate every step inside Surpac. In this tutorial, **grade estimation is carried out only for Total Copper (TCu)**.

## Project Overview

Surpac (by Dassault Systèmes / GEOVIA) is one of the most widely used geological and mine planning software packages in the mining industry. This project demonstrates the practical use of Surpac for translating subsurface exploration data into a usable open-pit design. The workflow is built around a multi-campaign **copper-cobalt (Cu-Co) exploration dataset** and is structured for students and early-career mining engineers who want a clear, hands-on path through the software.

The tutorial covers the typical pipeline used in resource and reserve estimation studies:

- Importing and validating drillhole data (collar, survey, assay, and lithology tables).
- Visualizing drillholes in 3D and creating cross-sections.
- Compositing TCu assays and applying geological constraints.
- Building a block model and assigning grade attributes for TCu.
- Performing grade estimation for **TCu only**, using interpolation methods such as inverse distance weighting.
- Designing pit shells, benches, ramps, and final pit limits.
- Generating volumes, tonnages, and visual outputs for reporting.

> **Note on scope of estimation:** Although the assay table contains TCu, TCo, ASCu, and ASCo values, this tutorial estimates grades for **TCu (Total Copper) only**. The other assay fields (TCo, ASCu, ASCo) are retained in the database for reference but are not interpolated into the block model.

## Repository Contents

- **Surpac_Tutorial_compressed (2).pdf** — Step-by-step tutorial that walks through the full Surpac workflow from drillhole import to pit design (with TCu grade estimation), including screenshots and explanatory notes.
- **Collar-1.csv** — Drillhole collar table (one record per hole) with hole location and total depth.
- **Survey12.csv** — Downhole survey table with azimuth and dip readings at depth intervals.
- **Assay-1.csv** — Sample assay table with Cu and Co grades over downhole sample intervals (only TCu is used for estimation in this tutorial).
- **Geology-1.csv** — Geological logging table assigning a stratigraphic / lithological code to each downhole interval.

## Dataset Description

The dataset represents a Cu-Co exploration program covering multiple drilling campaigns and project areas. It is provided purely as a teaching dataset to accompany the tutorial.

### Collar table (Collar-1.csv)

Columns: `Project, hole_id, y, x, z, max_depth`

- **Project** — Project / campaign code (see "Project codes" below).
- **hole_id** — Unique drillhole identifier within the project.
- **y, x, z** — Northing, Easting, and Elevation of the collar, assumed to be in a local UTM grid (Southern Hemisphere). Units: metres.
- **max_depth** — Total drilled length of the hole, in metres.

### Survey table (Survey12.csv)

Columns: `Project, hole_id, depth, azimuth, dip`

- **depth** — Downhole depth at which the survey reading was taken (metres).
- **azimuth** — Hole bearing in degrees.
- **dip** — Hole inclination in degrees (-90° = vertical, downward).

### Assay table (Assay-1.csv)

Columns: `Project, hole_id, samp_id, depth_from, depth_to, TCu, TCo, ASCu, ASCo, Description`

- **samp_id** — Sample identifier.
- **depth_from / depth_to** — Sample interval in metres downhole.
- **TCu** — Total Copper grade (%). **This is the variable used for grade estimation in the tutorial.**
- **TCo** — Total Cobalt grade (%). Included for reference; not estimated in this tutorial.
- **ASCu** — Acid Soluble Copper grade (%). Included for reference; not estimated in this tutorial.
- **ASCo** — Acid Soluble Cobalt grade (%). Included for reference; not estimated in this tutorial.
- **Description** — Free-text sample description / notes.

### Geology table (Geology-1.csv)

Columns: `Project, hole_id, depth_from, depth_to, ModelStratigraphy`

- **depth_from / depth_to** — Logged interval in metres downhole.
- **ModelStratigraphy** — Stratigraphic / lithological code assigned to the interval, used to build geological wireframes and constrain estimation.

### Project codes

The dataset combines several drilling campaigns / project areas, identified by the following codes in the `Project` column: **CM, MR, OXS, OXY, RPD, RSP, RSS**. Each code groups holes that belong to a particular campaign or area within the broader exploration program.

## Workflow Summary

The high-level workflow followed in this tutorial, using the included dataset, is:

1. **Drillhole Database Setup** — Import the Collar, Survey, Assay, and Geology CSV files into Surpac and validate the database.
2. **Data Visualization** — Display drillholes in 3D, generate sections, and inspect data quality.
3. **Compositing** — Composite **TCu** assay data over fixed downhole intervals for use in estimation.
4. **Geological Modeling** — Create solids/wireframes representing ore zones using the ModelStratigraphy codes.
5. **Block Model Creation** — Build an empty block model constrained to the geological wireframes, with **TCu** defined as the grade attribute.
6. **Grade Estimation (TCu only)** — Populate the block model with **Total Copper (TCu)** grades using an interpolation method such as inverse distance weighting. Other elements (TCo, ASCu, ASCo) are not estimated in this tutorial.
7. **Pit Design** — Define bench heights, batter angles, berm widths, and ramp geometry to construct an open-pit design.
8. **Reporting & Visualization** — Calculate volumes/tonnages for TCu and produce visual outputs for review.

## Intended Audience

This material is most useful for:

- Mining engineering students learning Surpac for the first time.
- Early-career engineers and geologists who want a refresher on the drillhole-to-pit-design pipeline.
- Educators looking for a structured walkthrough, with a ready-to-use Cu-Co dataset, to support coursework on mine planning and resource estimation.

## How to Use

1. Open **Surpac_Tutorial_compressed (2).pdf** and read through the workflow.
2. In Surpac, set up a new project and import the four CSV files as the Collar, Survey, Assay, and Geology tables of a drillhole database.
3. Follow each step in the tutorial against the imported dataset to build the block model, estimate TCu, and produce the pit design.

## Author

Maintained by [Pratik Kumar](https://github.com/Pratik-Kumar887).

## Disclaimer

This repository is shared for **academic and educational purposes only**. The included dataset is provided as a teaching dataset for use with the Surpac tutorial; it should not be interpreted as a representation of any specific commercial deposit, project, or resource estimate. *Surpac* and *GEOVIA* are trademarks of Dassault Systèmes and are referenced here solely to describe the software workflow demonstrated in the tutorial.
