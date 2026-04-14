---
theme: default
title: Resilient Hydro Twin – System Updates
info: Recent Platform Improvements
class: text-center
highlighter: shiki
transition: slide-left
---
 
# Resilient Hydro Twin  
## Platform Updates Overview

---

# Agenda

- Current access and platform status
- What has been added recently
- Scenario and GeoTIFF workflow
- Planning interface improvements
- What is next

---

# Current Status

## Access and infrastructure

- GitLab is currently not accessible
- HTTPS for the website is not yet enabled
- The GitHub repository can be used instead
- Team members can join GitHub to access the repository
- Issues can also be created and tracked there

---

# Recent Updates

## Platform and admin workflow

- Added an admin workflow for intervention scenarios
- Users can create scenarios from the planning interface
- Admin users can review these scenarios
- GeoJSON export is available for saved scenarios
- Admin users can now import GeoTIFF outputs for an existing scenario
- Admin users can also include new scenarios created outside the system

---

# Scenario and GeoTIFF Workflow

## Current flow

- Users create intervention scenarios in the planning interface
- Human-in-the-loop review happens afterward
- Simulation outputs are generated as GeoTIFF files
- GeoTIFF folders can be uploaded into the system
- Scenario metadata is read and shown in the admin table
- Uploaded scenarios become available in the platform workflow

---

# Raster Visualization

## GeoTIFF handling

- TiTiler is used for serving and visualizing GeoTIFF files
- Raster outputs can be browsed in the Scenarios tab
- TIFF sequences can be selected and played on the map
- Scenario metadata is shown together with raster outputs
- This supports direct inspection of imported model results

---

# Planning Interface Updates

## User-facing improvements

- Aggregation areas are loaded and shown on the map
- Users can select aggregation areas by city and type
- Intervention drawing and scenario building are integrated in one workflow
- The map-based planning workspace has been improved
- The tab/workspace area under the map has been reorganized for clearer navigation

---

# Data and Spatial Layers

## Added capabilities

- Aggregation areas are integrated into the planning interface
- Scenario packages can now connect user-created interventions with imported model outputs
- External scenarios can be uploaded with metadata and raster files
- This improves traceability between planning inputs and simulation results

---

# Next Items

## Upcoming technical work

- Integration of SFINCS
- Integration of Delft-FIAT
- Knowledge graph development
- Continued workflow integration between scenarios, simulations, and outputs
- Further platform hardening, including HTTPS and access improvements

---

# Recap


- Core scenario management and GeoTIFF upload workflows are now in place
- TiTiler supports serving the raster outputs in the interface
- Aggregation areas and planning features are connected more clearly
- The next focus is model integration and knowledge graph work
