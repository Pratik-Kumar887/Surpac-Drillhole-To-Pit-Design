# Surpac — Drillhole to Pit Design Workflow

This repository documents an end-to-end **Surpac** workflow that takes raw exploration drillhole data and develops it into a complete **open-pit mine design**. It is intended as a learning resource and reference guide that walks through the major steps a mining engineer follows inside Surpac, from data import all the way to pit visualization.

## Project Overview

Surpac (by Dassault Systèmes / GEOVIA) is one of the most widely used geological and mine planning software packages in the mining industry. This project demonstrates the practical use of Surpac for translating subsurface exploration data into a usable open-pit design. The workflow shown here is structured for students and early-career mining engineers who want a clear, hands-on path through the software.

The tutorial covers the typical pipeline used in resource and reserve estimation studies:

- Importing and validating drillhole data (collar, survey, assay, and lithology tables).
- Visualizing drillholes in 3D and creating cross-sections.
- Compositing assays and applying geological constraints.
- Building a block model and assigning grade attributes.
- Performing grade estimation (e.g., inverse distance or kriging where applicable).
- Designing pit shells, benches, ramps, and final pit limits.
- Generating volumes, tonnages, and visual outputs for reporting.

## Repository Contents

- **Surpac_Tutorial_compressed (2).pdf** — A compressed PDF tutorial that walks step-by-step through the Surpac workflow from drillhole import to pit design, including screenshots and explanatory notes for each stage.

## Workflow Summary

The high-level workflow followed in this tutorial is:

1. **Drillhole Database Setup** — Import collar, survey, assay, and lithology files and validate the database.
2. **Data Visualization** — Display drillholes in 3D, generate sections, and inspect data quality.
3. **Compositing** — Composite assay data over fixed intervals for use in estimation.
4. **Geological Modeling** — Create solids/wireframes representing ore zones or lithological domains.
5. **Block Model Creation** — Build an empty block model and constrain it to the geological wireframes.
6. **Grade Estimation** — Populate the block model using interpolation methods such as inverse distance weighting.
7. **Pit Design** — Define bench heights, batter angles, berm widths, and ramp geometry to construct an open-pit design.
8. **Reporting & Visualization** — Calculate volumes/tonnages and produce visual outputs for review.

## Intended Audience

This material is most useful for:

- Mining engineering students learning Surpac for the first time.
- Early-career engineers and geologists who want a refresher on the drillhole-to-pit-design pipeline.
- Educators looking for a structured walkthrough to support coursework on mine planning and resource estimation.

## How to Use

Open **Surpac_Tutorial_compressed (2).pdf** and follow the steps in order. It is recommended to replicate each step inside Surpac using a sample dataset (either the one provided with the Surpac installation or any teaching dataset available to you) to reinforce the concepts.

## Author

Maintained by [Pratik Kumar](https://github.com/Pratik-Kumar887).

## Disclaimer

This repository is shared for **academic and educational purposes only**. *Surpac* and *GEOVIA* are trademarks of Dassault Systèmes and are referenced here solely to describe the software workflow demonstrated in the tutorial. No proprietary data, licensed software, or confidential information is distributed through this repository.
