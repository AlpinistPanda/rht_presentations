---
theme: default
title: Resilient Hydro Twin — Participatory Digital Twin for Urban Flood Resilience
info: |
  Conference presentation — Özgün Balaban, 2026

highlighter: shiki
drawings:
  persist: false
transition: slide-left
mdc: true
---

<div class="flex justify-between">
<h2>Prelude - tragedy</h2>
<h2 class="text-xs font-thin">Chennai 2015</h2>
</div>

<div class="flex justify-center">

<img src="/img/news.png" class="w-1/2 ">

</div>
<!--


In October 2015, Chennai received in 24 hours what normally falls in a month.

Five hundred people died. Four million were displaced. Damage ran into billions of dollars.

I want you to hold that image for a moment — not the statistics, but what it actually means.
Families on rooftops. Hospitals without power. Entire neighbourhoods cut off for days.

And here is what makes this research relevant: the city had data. It had sophisticated
hydrological models. It had engineers who understood exactly how the drainage system
behaved under stress.

What it did not have — what almost no city has — is a way to turn that knowledge into
collaborative decisions, fast enough, and open enough, to actually change outcomes.

-

That gap — between what we know and what we decide — is precisely what this research addresses."


-->



---

# Prelude - numbers

<iframe src="https://ourworldindata.org/grapher/natural-disasters-by-type?tab=chart" loading="lazy" style="width: 100%; height: 450px; border: 0px none;" allow="web-share; clipboard-write"></iframe>

<!--

Urban flooding is one of the most costly natural disaster category on the planet.
And it is accelerating — more intense rainfall, higher sea levels, more people living in flood-exposed urban areas.

-->

---

## Prelude - decision making

<div v-click class="border border-gray rounded-xl absolute right-150px top-200px">
<mdi-account class="text-9xl text-red-400"/>
<div class="flex justify-center">
<span class="text-xl">Planner</span>
</div>
</div>

<div v-click class="border border-gray rounded-xl absolute left-100px top-70px w-1/3 p-2">

<img src="/img/model.png" class="">
<div class="flex justify-center">
<span>Simulation Models</span>
</div>
</div>

<div v-click class="border border-gray rounded-xl absolute left-100px bottom-50px w-1/3">
<div class="flex justify-center">
<img src="/img/data.jpg" class="h-150px p-2">
</div>
<div class="flex justify-center">
<span>Urban Data</span>
</div>
</div>

<Arrow v-click="3" x1="430" y1="150" x2="660" y2="300" text-gray/>

<Arrow v-click="3" x1="430" y1="420" x2="660" y2="310" text-gray/>

<!--
Now — if you are a city planner in Rotterdam, or Chennai, or anywhere, and you need to decide whether to build a water square, retrofit green roofs across a district, or reroute a drainage channel — what tools do you actually reach for?

-

There are powerful hydrological models. Mike+, SFINCS, Delft3D. But they require specialist knowledge to configure and run. Their outputs arrive as large raster files in formats that most planning offices cannot open. The simulations exist, but they live behind a wall of technical complexity.

And critically — the participatory dimension is almost entirely absent. The urban planner who needs to make the decision, the community that will live with the consequences — they are downstream of the science, not part of it.

There is often no shortage of data. There is no shortage of models. What is scarce — what is almost universally absent — is the layer that connects the two to the people who need to act.

That is the gap this platform is designed to close."

-->




---

<div class="w-full h-full flex bg-white">

  <!-- Left panel — titles + speaker card -->
  <div class="flex flex-col justify-center w-1/2 h-full">
    <h2 class="text-sm font-medium text-slate-900 leading-tight mb-8">
      A Modular Knowledge Driven Digital Twin Architecture for Urban Flood Resilience
    </h2>
    <h3>Resilient Hydro Twin</h3>
    <div class="flex flex-col">
        <SpeakerCard class="w-1/2 p-2 m-2" name="Özgün Balaban" affiliation="TU Eindhoven"></SpeakerCard>
        <SpeakerCard class="w-1/2 p-2 m-2" name="Pieter Pauwels" affiliation="TU Eindhoven"></SpeakerCard>
    </div>
  </div>
  

  <!-- Right panel — Chennai image placeholder -->
  <div class="w-1/2 h-full relative overflow-hidden bg-slate-100 flex items-center justify-center">
    <!-- Placeholder box -->
  <img src="/img/project_card.png" class="">
  </div>
</div>


---

# Resilient Hydro Twin

<v-click>

- consortium-led research effort focused on <span v-mark.circle.orange="1">improving urban flood resilience.</span>

<img src="/img/partners.png">

</v-click>

<v-click>

- city-scale digital twin platform — designed to bring hydrodynamic simulation and urban decision-making into the same environment.

- integrates models, urban systems, and human decision-making into a single interactive layer.
</v-click>

<v-click class="py-2">

<div class="flex justify-center">
<div class="border m-2 p-2">
Planning Interface
</div>
<div class="border m-2 p-2">
Reporting Interface
</div>
<div class="border m-2 p-2">
Real Time Monitoring Interface
</div>
</div>


</v-click>

<!--

“So what would it look like to actually close this gap?

Resilient Hydro Twin is a consortium-led research effort focused on improving urban flood resilience.

And at its core is a city-scale digital twin platform — designed to bring hydrodynamic simulation and urban decision-making into the same environment.

It integrates models, urban systems, and human decision-making into a single interactive layer.

And it is structured around three interconnected interfaces.

A planning interface.

A reporting interface.

And a real time monitoring interface.

-

Today, I will focus on the planning interface.

Because this is where the gap we identified becomes most visible —
and where it is actually resolved.

Let me show you how it works.”

-->

---


# Multi-City Deployment

<div class="grid grid-cols-2 gap-12 mt-8">

<div class="text-center">

### Rotterdam, Netherlands



<div class="border rounded-xl p-6 mt-4 text-left text-sm">

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

<div class="border rounded-xl p-6 mt-4 text-left text-sm">

- Monsoon-driven flood regime
- Rapid urban expansion
- Limited drainage infrastructure
- Custom catchment delineation
- Intensities: 10–100 mm/h

</div>
</div>

</div>

---


# Live demo

<!--



"So let me show you what we built.

  

What you are looking at is the Resilient Hydro Twin planning interface. A city planner —

no specialist hydrology training required — has opened this in their browser.

  

On the map, you can see a live flood simulation for Rotterdam under a 50 millimetre per

hour rainfall event. The blue overlay is water depth — mapped at high resolution across

every street, every district.

  

Now the planner draws. Directly on the map, they sketch a green roof intervention zone

over this neighbourhood. The system logs it as an intervention area — typed, geolocated, saved.

  

[PAUSE]

  

They bundle this with a base flood scenario into what we call an Intervention Scenario.

And the platform returns the comparison: water depth before and after. Flow velocity.

Economic damage — estimated in euros, aggregated at the neighbourhood level.

  

In this case — a green roof intervention over this district, under a 50 millimetre event —

the platform estimates a 31 percent reduction in economic damage.

  

That number is not the point. The point is that a planner just ran a flood experiment

in their browser, without a hydrologist in the room, and got a spatially explicit,

quantified answer.

  

That is new. And that is the core contribution."

  

DIRECTOR: This is the film's climax. Slow down at 'now the planner draws'. Point at the slide

like you're showing a colleague something exciting. '31 percent reduction' — plain delivery,

then immediately pivot: 'that number is not the point.' Stillness on that line.


-->

---

# Demo alternative -- Authentication

<img src="/img/admin.png">

---

# Demo alternative -- Scenario creation / Interventions

<img src="/img/interventions.png">

---

# Demo alternative -- Results

<img src="/img/results.png">

---
layout: default
---

# System Architecture

<ArchSlide />

<!--
"Let me briefly open the hood.

At the core is the hydrological models SFINCS and MIKE+.

It solves the shallow water equations at high spatial resolution across the city grid.

This is the scientific engine. It is well-validated, widely used in flood research,

and our platform wraps it rather than replaces it.

  

The pipeline works like this: a planner's intervention — drawn as a polygon on the map —

is submitted to the Django REST backend. The backend passes it to SFINCS along with

the rainfall scenario and city geometry. SFINCS runs the simulation and writes the outputs

— water depth, flow velocity, economic damage — as Cloud-Optimized GeoTIFFs.

  

Those GeoTIFFs are served live to the browser via TiTiler — a FastAPI tile server that

reads COG files and generates XYZ map tiles on demand. No pre-processing, no duplication.

A city-wide raster dataset streams to the browser in sub-second tile rendering.

  

Underneath this sits a formal OWL ontology — every concept in the platform, every

intervention type, every scenario, every simulation variable, is a typed, formally defined

class. This is what makes the platform interoperable: it can connect to GIS systems,

BIM tools, and external climate datasets without custom integration work.

  

The entire stack runs in Docker Compose, deployed on SURF Research Cloud, and is

fully open source."

  

DIRECTOR: Deliver technical content with confidence, no apology. Short declarative sentences.

The final 'fully open source' — slow down. It matters to both halves of the room.
-->

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



---


# Contributions

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

<!--




"Let me close by being precise about what this research contributes — because I think there are four things here, and they operate at different levels.

First: a participatory digital twin architecture. We have extended traditional hydrological

simulation with an interactive, web-based planning layer. The model is no longer behind a wall.

Non-expert stakeholders — planners, community representatives, decision-makers — can now

co-design flood interventions without specialist training.

  

  

Third: a real-time raster streaming architecture using Cloud-Optimized GeoTIFFs and TiTiler.

This delivers large-scale simulation outputs — city-wide, high-resolution rasters — to a

standard browser at sub-second tile rendering. No pre-processing pipeline. No data duplication.

This is a non-trivial engineering contribution for anyone working with large geospatial

simulation outputs.

  


[PAUSE — 2 full seconds]

-->


---

# Future

<!--



Cities are going to flood more. That is not a prediction — it is already happening.

The question is whether the people responsible for those cities have tools that match

the scale of that problem.

  

Resilient Hydro Twin is our answer to that question.

  

Thank you."

  

DIRECTOR: Four contributions — measured pace, no rushing. After the fourth, pause fully.

The closing two sentences echo Act 1. Say them slowly. 'Thank you.' Full stop.

Do NOT say 'any questions' or 'so yes, that's it'. Let the MC take over.

-->


