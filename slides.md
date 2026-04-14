---
theme: default
title: Resilient Hydro Twin — Digital Twin Platform for Urban Flood Resilience
info: |
  Conference presentation for the Resilient Hydro Twin (RHT) project.
  A participatory digital twin platform for urban flood simulation and
  climate adaptation planning, deployed for Rotterdam and Chennai.
class: text-center
highlighter: shiki
drawings:
  persist: false
transition: slide-left
mdc: true
layout: cover
background: '#0f172a'
---

# Resilient Hydro Twin

**A Participatory Digital Twin Platform for Urban Flood Resilience**

<div class="mt-4 text-blue-300 text-lg">
Rotterdam · Chennai · Climate Adaptation at Scale
</div>

<div class="mt-8 text-slate-400 text-sm">
Özgün Balaban — 2026
</div>

<!--
[IMAGE PLACEHOLDER: Full-bleed aerial/satellite image of a city with flood overlay visualization —
showing blue flood water extent mapped over urban street grid. Ideally Rotterdam or Chennai.
Overlay a subtle dark gradient so text remains readable.]
-->

---
layout: intro
---

# The Urban Flood Challenge

<div class="grid grid-cols-2 gap-8 mt-6">
<div>

### The Problem
- Urban flooding is the **#1 most costly natural disaster** globally
- Climate change intensifies rainfall events and raises sea levels
- Cities lack tools to **evaluate adaptation strategies** before they build
- Decision-makers need evidence, not intuition

</div>
<div>

### The Gap
- Hydrological models exist but are **inaccessible** to planners
- 3D simulations are siloed in research labs
- **No participatory layer** — citizens and planners cannot interact
- Data is abundant; **actionable insight** is scarce

</div>
</div>

<!--
[IMAGE PLACEHOLDER: Split image — left side: flooded street in a Dutch or Indian city with cars submerged.
Right side: a planner at a desk surrounded by paper maps and spreadsheets, looking overwhelmed.
Emphasizes the gap between raw data and decision-making.]
-->

---
layout: center
---

# Introducing Resilient Hydro Twin

<div class="text-xl text-slate-300 mt-2 mb-8">
An open-source, cloud-ready digital twin for simulating urban floods,<br/>
planning interventions, and assessing city resilience — interactively.
</div>

```
         User / Planner / Researcher
                    │
         ┌──────────▼──────────┐
         │   Interactive Web   │  ← Draw, explore, compare
         │   Planning Interface│
         └──────────┬──────────┘
                    │
      ┌─────────────┼──────────────┐
      │             │              │
  ┌───▼───┐   ┌─────▼─────┐  ┌────▼────┐
  │SFINCS │   │ REST API  │  │ Raster  │
  │ Model │   │  Backend  │  │  Tiles  │
  └───────┘   └─────┬─────┘  └─────────┘
                    │
             ┌──────▼──────┐
             │  PostgreSQL │
             └─────────────┘
```

<!--
[IMAGE PLACEHOLDER: Clean system architecture diagram with icons for each service:
- Browser icon (Frontend / SvelteKit)
- Server rack icon (Django Backend)
- Map tile icon (TiTiler)
- Cylinder icon (PostgreSQL)
- Wave icon (SFINCS model)
Use a dark background with blue/cyan connecting lines and Lucide-style icons.]
-->

---
layout: two-cols
---

# Platform Architecture

## Services

- **SvelteKit Frontend** — MapLibre GL 3D map, drawing tools, scenario explorer
- **Django REST API** — Auth, scenarios, interventions, spatial data
- **TiTiler** — Streams GeoTIFF rasters as live map tiles
- **PostgreSQL** — Users, scenarios, geometries, logs
- **NGINX** — Reverse proxy + static files + SSL-ready

<br/>

## Deployment

- Fully **Dockerized** via Docker Compose
- **CI/CD** on GitLab → SURF Research Cloud
- Raster data mounted externally (scalable multi-city datasets)

::right::

<!--
[IMAGE PLACEHOLDER: Docker Compose service graph rendered as a clean network diagram.
Show 5 rounded rectangle nodes (Frontend, Backend, TiTiler, PostgreSQL, NGINX)
connected by labelled arrows indicating data flow.
Color-code: NGINX = grey, Frontend = purple, Backend = green, TiTiler = teal, DB = orange.
Background: dark slate.]
-->

<div class="mt-16 p-4 bg-slate-800 rounded-lg text-sm font-mono text-blue-300">

```
nginx → frontend   :3000
nginx → backend    :8000
nginx → titiler    :8080
backend → postgres :5432
titiler → rasters  /data/rasters
```

</div>

---
layout: image-right
image: 'placeholder-map-interface.png'
---

# Interactive Planning Interface

## What users can do

1. **Visualize flood scenarios** — 5 rainfall intensities (10–100 mm/h)
2. **Draw interventions** directly on the 3D map
3. **Bundle into scenarios** — combine multiple interventions
4. **Compare outcomes** — before vs. after resilience assessment
5. **Export to GeoJSON** — share and collaborate

<br/>

## Intervention Types

| Type | Description |
|---|---|
| Water squares | Underground storage tanks |
| Thin dams | Compartmentalization barriers |
| Green roofs | Pervious surface coverage |
| Permeable pavement | Infiltration-based reduction |
| Urban parks | Vegetation & detention basins |

<!--
[IMAGE PLACEHOLDER (right panel): Screenshot or mockup of the planning interface.
Show MapLibre GL map of Rotterdam with:
- Blue flood depth raster overlay on city streets
- Yellow/green polygon drawn over a neighborhood (intervention area)
- Left sidebar with intervention type selector (icons + labels)
- Top bar with scenario name and rainfall intensity slider
Dark map basemap with vibrant overlay colors.]
-->

---
layout: center
---

# Flood Simulation Pipeline

<div class="grid grid-cols-3 gap-6 mt-8 text-center">

<div class="bg-slate-800 rounded-xl p-6">
  <div class="text-3xl mb-3">🌧️</div>
  <div class="font-bold text-blue-300">Input</div>
  <div class="text-sm text-slate-300 mt-2">
    Rainfall scenario<br/>
    (10–100 mm/h)<br/>
    City geometry (GIS)<br/>
    Intervention polygons
  </div>
</div>

<div class="bg-slate-800 rounded-xl p-6">
  <div class="text-3xl mb-3">⚙️</div>
  <div class="font-bold text-blue-300">SFINCS Model</div>
  <div class="text-sm text-slate-300 mt-2">
    Shallow water equations<br/>
    High-resolution grid<br/>
    Hydrodynamic routing<br/>
    Damage estimation
  </div>
</div>

<div class="bg-slate-800 rounded-xl p-6">
  <div class="text-3xl mb-3">🗺️</div>
  <div class="font-bold text-blue-300">Output</div>
  <div class="text-sm text-slate-300 mt-2">
    Water depth (m)<br/>
    Flow velocity (m/s)<br/>
    Water level (m NAP)<br/>
    Economic damage (€)
  </div>
</div>

</div>

<div class="mt-8 text-slate-400 text-sm">
Outputs delivered as <strong>Cloud-Optimized GeoTIFFs (COG)</strong> → streamed live via TiTiler
</div>

<!--
[IMAGE PLACEHOLDER: Three-panel horizontal flow diagram.
Panel 1 (Input): stylized rainfall icon over a city block grid with colored polygon overlays.
Panel 2 (SFINCS): animated wave equation graphic or computational mesh grid with depth values.
Panel 3 (Output): colormap raster on city map — blues for depth, oranges for velocity, reds for damage.
Connect panels with large right-pointing arrows. Dark background, use bright icon colors.]
-->

---
layout: two-cols
---

# Semantic Ontology

The platform is backed by a **formal RDF/OWL ontology** (`rhdt.ttl`) that defines all domain concepts:

<br/>

**Core Classes**
- `InterventionScenario` — bundled plan
- `InterventionArea` — individual polygon + type
- `RasterScenario` — simulation output folder
- `AggregationArea` — neighborhoods / catchments
- `BaseScenario` — reference flood event

<br/>

**Why an Ontology?**
- Enables **linked data** and SPARQL queries
- Supports **interoperability** with external GIS/BIM systems
- Provides formal validation of domain logic
- Foundation for **knowledge graph** extensions

::right::

<!--
[IMAGE PLACEHOLDER: OWL class hierarchy diagram rendered as a tree/graph.
Root node: "RHT Domain" → branches to:
  InterventionScenario → (hasCity, hasClimateScenario, includesIntervention)
  InterventionArea → (hasInterventionType, geoJson)
  RasterScenario → (containsFrame, variable, timestamp)
  AggregationArea → (hasAggregationType, coversArea)
Use rounded rectangles for classes, labelled arrows for object properties.
Color-code by class type. Dark slate background.]
-->

<div class="mt-4 text-xs font-mono bg-slate-900 rounded-lg p-4 text-green-300">

```turtle
:InterventionScenario a owl:Class ;
  rdfs:label "Intervention Scenario" .

:includesIntervention a owl:ObjectProperty ;
  rdfs:domain :InterventionScenario ;
  rdfs:range  :InterventionArea .

:hasCity a owl:ObjectProperty ;
  rdfs:range :City .

:Rotterdam a :City ;
  rdfs:label "Rotterdam, NL" .

:Chennai a :City ;
  rdfs:label "Chennai, India" .
```

</div>

---
layout: center
---

# Multi-City Deployment

<div class="grid grid-cols-2 gap-12 mt-8">

<div class="text-center">

### Rotterdam, Netherlands

<!--
[IMAGE PLACEHOLDER: Aerial map of Rotterdam with flood risk zones highlighted.
Show the river Maas, port area, and residential neighborhoods.
Use semi-transparent blue flood extent overlay.
Add small legend: return periods 10yr / 25yr / 50yr.]
-->

<div class="bg-slate-800 rounded-xl p-6 mt-4 text-left text-sm">

- River delta + coastal exposure
- Dense urban morphology
- Advanced water management legacy
- PDOK/CBS neighborhood data
- Return periods: 10–100 yr

</div>
</div>

<div class="text-center">

### Chennai (Tambaram), India

<!--
[IMAGE PLACEHOLDER: Aerial map of Chennai/Tambaram with flood-prone areas highlighted.
Show coastal areas, low-lying urban zones, and drainage channels.
Use orange-to-red overlay for risk zones (different palette from Rotterdam).
Add small legend: rainfall intensity mm/h.]
-->

<div class="bg-slate-800 rounded-xl p-6 mt-4 text-left text-sm">

- Monsoon-driven flood regime
- Rapid urban expansion
- Limited drainage infrastructure
- Custom catchment delineation
- Intensities: 10–100 mm/h

</div>
</div>

</div>

---
layout: two-cols
---

# User & Access Workflow

The platform is designed for **multi-stakeholder collaboration**:

<br/>

**Roles**
- **Researchers** — run simulations, export data
- **Urban planners** — design interventions, compare scenarios
- **Decision-makers** — review aggregated resilience assessments
- **Platform admins** — approve users, manage content

<br/>

**Access Flow**
1. User registers → status: *pending*
2. Admin reviews → *approves* or rejects
3. JWT token issued → full platform access
4. All actions logged with user attribution

::right::

<!--
[IMAGE PLACEHOLDER: User flow diagram (vertical swimlane style).
Three lanes: User | Platform | Admin.
Steps:
  1. User submits signup form
  2. Platform stores as "pending"
  3. Admin reviews in dashboard
  4. Admin clicks "Approve"
  5. Platform issues JWT token
  6. User accesses planning interface
Use clean flowchart shapes. Blue = User actions, green = System, orange = Admin.]
-->

<div class="mt-8 bg-slate-800 rounded-xl p-4 text-sm">

**API Endpoints**
```
POST /api/signup/
POST /api/token/
GET  /api/me/
GET  /api/admin/registrations/
POST /api/admin/registrations/{id}/approve/
GET  /api/scenarios/
POST /api/interventions/
POST /api/intervention-scenarios/
GET  /api/rasters/
GET  /api/aggregation-areas/geojson/
```

</div>

---
layout: center
---

# Resilience Assessment

How the platform quantifies flood impact **before and after** intervention:

<div class="grid grid-cols-3 gap-6 mt-8">

<div class="bg-blue-900/50 border border-blue-700 rounded-xl p-5 text-center">
  <div class="text-2xl font-bold text-blue-300">Water Depth</div>
  <div class="text-4xl my-3">🌊</div>
  <div class="text-sm text-slate-300">
    Per-pixel depth in meters<br/>
    Colormap: Blues<br/>
    Aggregated by neighborhood
  </div>
</div>

<div class="bg-orange-900/50 border border-orange-700 rounded-xl p-5 text-center">
  <div class="text-2xl font-bold text-orange-300">Flow Velocity</div>
  <div class="text-4xl my-3">💨</div>
  <div class="text-sm text-slate-300">
    m/s at each grid cell<br/>
    Colormap: Oranges<br/>
    Risk to pedestrians & vehicles
  </div>
</div>

<div class="bg-red-900/50 border border-red-700 rounded-xl p-5 text-center">
  <div class="text-2xl font-bold text-red-300">Economic Damage</div>
  <div class="text-4xl my-3">💶</div>
  <div class="text-sm text-slate-300">
    Euro damage estimate<br/>
    Colormap: Reds<br/>
    District-level aggregation
  </div>
</div>

</div>

<div class="mt-6 text-slate-400 text-sm">
Spatial aggregation across <strong>neighborhoods · districts · catchments</strong>
</div>

<!--
[IMAGE PLACEHOLDER: Three side-by-side map panels showing the same neighborhood.
Panel 1: Blue choropleth — water depth gradient.
Panel 2: Orange choropleth — flow velocity gradient.
Panel 3: Red choropleth — economic damage gradient.
Each panel shows Rotterdam's Feijenoord or similar dense district.
Below each: bar chart showing the metric aggregated by sub-neighborhood.
Dark basemap, vivid colormaps, clear legends.]
-->

---
layout: center
---

# Technology Stack

<div class="grid grid-cols-4 gap-4 mt-8 text-sm text-center">

<div class="bg-slate-800 rounded-xl p-4">
  <div class="text-blue-300 font-bold text-base mb-2">Frontend</div>
  <div class="text-slate-300">SvelteKit 2<br/>Svelte 5<br/>MapLibre GL 4<br/>TypeScript 5<br/>Vite 7</div>
</div>

<div class="bg-slate-800 rounded-xl p-4">
  <div class="text-green-300 font-bold text-base mb-2">Backend</div>
  <div class="text-slate-300">Django 5<br/>DRF 3.15<br/>PostgreSQL 16<br/>PostGIS<br/>Gunicorn</div>
</div>

<div class="bg-slate-800 rounded-xl p-4">
  <div class="text-teal-300 font-bold text-base mb-2">Geospatial</div>
  <div class="text-slate-300">TiTiler<br/>COG GeoTIFF<br/>GeoJSON<br/>SFINCS<br/>PDOK/CBS</div>
</div>

<div class="bg-slate-800 rounded-xl p-4">
  <div class="text-purple-300 font-bold text-base mb-2">DevOps</div>
  <div class="text-slate-300">Docker Compose<br/>NGINX Alpine<br/>GitLab CI/CD<br/>SURF Cloud<br/>RDF/OWL</div>
</div>

</div>

<!--
[IMAGE PLACEHOLDER: Technology stack logo wall — arrange official logos in a 4x4 grid:
Row 1 (Frontend): SvelteKit, MapLibre GL, TypeScript, Vite
Row 2 (Backend): Django, DRF, PostgreSQL, PostGIS  
Row 3 (Geo): TiTiler, GeoTIFF (GDAL), GeoJSON, SFINCS
Row 4 (Infra): Docker, NGINX, GitLab, SURF Research Cloud
Dark background, logos at ~48px, labels beneath each. Subtle grid lines separating rows.]
-->

---
layout: center
---

# Data Flow: End-to-End

<div class="mt-6 text-sm">

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  1. PLAN       │  User draws polygons on map, selects intervention types      │
│                │  → POST /api/intervention-scenarios/                          │
├────────────────┼────────────────────────────────────────────────────────────┤
│  2. SIMULATE   │  SFINCS receives scenario → runs hydrodynamic model          │
│                │  → Writes COG GeoTIFFs to HOST_RASTER_ROOT/city-{id}-{slug}/ │
├────────────────┼────────────────────────────────────────────────────────────┤
│  3. DISCOVER   │  Backend scans raster folder → GET /api/rasters/             │
│                │  → Returns frame list: variable, timestamp, path              │
├────────────────┼────────────────────────────────────────────────────────────┤
│  4. TILE       │  TiTiler reads COG → generates XYZ tile pyramid on-demand    │
│                │  → GET /tiles/cog/tiles/{z}/{x}/{y}?url=file:///...           │
├────────────────┼────────────────────────────────────────────────────────────┤
│  5. VISUALIZE  │  MapLibre GL renders tile layer with colormap overlay         │
│                │  → User inspects depth, velocity, damage by area              │
└────────────────┴────────────────────────────────────────────────────────────┘
```

</div>

<!--
[IMAGE PLACEHOLDER: Animated sequence diagram (or static numbered swimlane):
5 horizontal rows (Plan → Simulate → Discover → Tile → Visualize)
with icons at each step:
  1. Map with drawing cursor icon
  2. CPU/wave equation icon
  3. File folder with scan icon
  4. Map tile pyramid icon
  5. Browser with colormap map icon
Left column has step number circles (1–5) in teal. Right shows the outcome.
Arrows connect each stage. Dark background, step numbers in bright teal circles.]
-->

---
layout: center
---

# Key Research Contributions

<div class="grid grid-cols-2 gap-8 mt-6">

<div class="bg-slate-800 rounded-xl p-6">
  <div class="text-blue-300 font-bold mb-3">Participatory Digital Twin</div>
  <p class="text-sm text-slate-300">
    Extends traditional simulation models with an <strong>interactive, web-based planning layer</strong> that enables non-expert stakeholders to co-design flood interventions — bridging the gap between hydrology and urban governance.
  </p>
</div>

<div class="bg-slate-800 rounded-xl p-6">
  <div class="text-green-300 font-bold mb-3">Semantic Interoperability</div>
  <p class="text-sm text-slate-300">
    An OWL ontology formally represents the domain, enabling <strong>linked data integration</strong> with GIS, BIM, and climate datasets — supporting multi-city, multi-model extensibility.
  </p>
</div>

<div class="bg-slate-800 rounded-xl p-6">
  <div class="text-orange-300 font-bold mb-3">Real-Time Raster Streaming</div>
  <p class="text-sm text-slate-300">
    COG + TiTiler architecture enables <strong>sub-second tile rendering</strong> of large GeoTIFF outputs without pre-tiling or data duplication — scalable to city-wide datasets.
  </p>
</div>

<div class="bg-slate-800 rounded-xl p-6">
  <div class="text-purple-300 font-bold mb-3">Comparative Resilience Scoring</div>
  <p class="text-sm text-slate-300">
    Quantitative before/after assessment at <strong>neighborhood and district scale</strong> across water depth, velocity, and economic damage — enabling evidence-based intervention prioritization.
  </p>
</div>

</div>

---
layout: center
---

# Live Demo

<!--
[IMAGE PLACEHOLDER: Annotated screenshot of the full planning interface in action.
Key callouts (with arrows):
  A → MapLibre GL flood raster overlay (blue depth map)
  B → Drawn intervention polygon (yellow outline over a district)
  C → Sidebar: intervention type selector with icons
  D → Top bar: scenario selector and rainfall intensity badge "50 mm/h"
  E → Bottom right: legend with colormap gradient (0m → 2m depth)
  F → Aggregation area boundaries (white district borders)
Caption: "Rotterdam — 50 mm/h scenario with green roof intervention, water depth output"
Dark map basemap, vivid overlays. 1920×1080 or 16:9 aspect ratio screenshot.]
-->

<div class="text-slate-400 mt-4">
Planning interface · Flood visualization · Intervention scenarios · Resilience metrics
</div>

---
layout: two-cols
---

# Roadmap & Future Work

## Near-term
- Real-time SFINCS **simulation queue** (Celery + Redis)
- Split-view **scenario comparison** (side-by-side map)
- **Cesium 3D** integration for building-level visualization
- **Kubernetes / Helm** deployment manifests

<br/>

## Research Directions
- Participatory evaluation with Rotterdam and Chennai stakeholders
- Machine learning surrogate models for faster simulation
- Integration with **digital building permits** (BIM)
- Multi-hazard extensions (heat, drought, compounding events)
- **Carbon co-benefits** quantification per intervention type

::right::

<!--
[IMAGE PLACEHOLDER: Roadmap timeline visualization.
Horizontal timeline with 4 milestones:
  Q1 2026: "Simulation Queue + Real-time Status"
  Q2 2026: "Split-View Comparison + 3D Cesium"
  Q3 2026: "Stakeholder Co-Design Sessions (Rotterdam/Chennai)"
  Q4 2026: "ML Surrogate + Multi-Hazard Extension"
Use color-coded milestone circles on a horizontal line.
Below the line: brief description labels.
Background: dark, accent colors in teal and purple.]
-->

<div class="mt-8 bg-slate-800 rounded-xl p-4 text-sm text-slate-300">

**Open Source**

The platform is open-source and designed for research adaptation.
Contributions welcome for:
- New city deployments
- Additional intervention types
- Alternative simulation backends

</div>

---
layout: center
---

# Summary

<div class="grid grid-cols-3 gap-6 mt-8 text-center">

<div>
  <div class="text-5xl font-bold text-blue-400">5</div>
  <div class="text-slate-300 mt-2">Rainfall Scenarios<br/>(10–100 mm/h)</div>
</div>

<div>
  <div class="text-5xl font-bold text-green-400">5</div>
  <div class="text-slate-300 mt-2">Intervention Types<br/>modeled & visualized</div>
</div>

<div>
  <div class="text-5xl font-bold text-purple-400">2</div>
  <div class="text-slate-300 mt-2">Pilot Cities<br/>Rotterdam · Chennai</div>
</div>

<div>
  <div class="text-5xl font-bold text-orange-400">4</div>
  <div class="text-slate-300 mt-2">Simulation Outputs<br/>depth · velocity · level · damage</div>
</div>

<div>
  <div class="text-5xl font-bold text-teal-400">3</div>
  <div class="text-slate-300 mt-2">Aggregation Levels<br/>neighborhood · district · catchment</div>
</div>

<div>
  <div class="text-5xl font-bold text-red-400">1</div>
  <div class="text-slate-300 mt-2">Open Platform<br/>participatory & extensible</div>
</div>

</div>

<!--
[IMAGE PLACEHOLDER: Collage of 4 map thumbnails arranged in a 2x2 grid:
  Top-left: Rotterdam flood depth map (blue)
  Top-right: Chennai rainfall scenario map (blue-green)
  Bottom-left: Intervention polygon drawing UI on Rotterdam map
  Bottom-right: Red damage choropleth on district level
Each thumbnail has a subtle rounded-corner frame and a small label badge.
Arrange against a dark background with subtle gradient dividers.]
-->

---
layout: cover
background: '#0f172a'
---

# Thank You

**Resilient Hydro Twin — Participatory Digital Twin for Urban Flood Resilience**

<div class="mt-6 text-slate-400">

GitHub: `resilienthydrotwin`  
Ontology: `rhdt.ttl` (RDF/OWL)  
Stack: SvelteKit · Django · MapLibre GL · TiTiler · PostgreSQL · Docker

</div>

<div class="mt-8 text-blue-300">
Questions & Discussion
</div>

<!--
[IMAGE PLACEHOLDER: Same aerial flood visualization as cover slide, but with a lighter overlay.
Or alternatively: a split composite showing Rotterdam on the left and Chennai on the right,
each with their respective flood raster overlay. Text remains centered on top.
Add a subtle "resilienthydrotwin" watermark in the bottom-right corner.]
-->
