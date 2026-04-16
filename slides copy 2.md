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
layout: image
image: /img/news.png
background: '#050d1a'
backgroundSize: 20em 70%
---

# Prelude

## Chennai 2015
<!--
SPEAKER NOTES — ACT 1 (0:00–2:00)

Start speaking before the room settles. No greeting. No title read-aloud.

"In October 2015, Chennai received in 24 hours what normally falls in a month.

Five hundred people died. Four million were displaced. Damage ran into billions of dollars.

I want you to hold that image for a moment — not the statistics, but what it actually means.
Families on rooftops. Hospitals without power. Entire neighbourhoods cut off for days.

And here is what makes this research urgent: the city had data. It had sophisticated
hydrological models. It had engineers who understood exactly how the drainage system
behaved under stress.

What it did not have — what almost no city has — is a way to turn that knowledge into
collaborative decisions, fast enough, and open enough, to actually change outcomes.

[PAUSE — full 2 seconds]

That gap — between what we know and what we decide — is precisely what this research addresses."

DIRECTOR: Slow down on each clause of the statistics. Pause is load-bearing — don't skip it.
IMAGE: Full-bleed aerial of flooded Chennai/Rotterdam streets. Dark gradient overlay bottom-left so text remains legible.
-->





---


<!--
SPEAKER NOTES — ACT 1 (0:00–2:00)
"Urban flooding is the single most costly natural disaster category on the planet.
And it is accelerating — more intense rainfall, higher sea levels, more people living
in flood-exposed urban areas.

-->

---



<!-- ═══════════════════════════════════════════
     ACT 1 — THE HOOK
     Slide: Split layout — text left, image right
     Time: 0:00 – 2:00
     ═══════════════════════════════════════════ -->

<div class="w-full h-full flex bg-white">

  <!-- Left panel — titles + speaker card -->
  <div class="flex flex-col justify-center px-16 py-16 w-1/2 h-full">
    <h1 class="text-xl font-medium text-slate-900 leading-tight mb-8">
      A Modular Knowledge-Driven Digital Twin Architecture for Urban Flood Resilience
    </h1>
  </div>
 
  
  
  

  <!-- Right panel — Chennai image placeholder -->
  <div class="w-1/2 h-full relative overflow-hidden bg-slate-100 flex items-center justify-center">
    <!-- Placeholder box -->
    <div class="absolute inset-0 flex flex-col items-center justify-end pb-8"
      style="background: linear-gradient(160deg, #cbd5e1 0%, #94a3b8 100%);">
      <div class="absolute inset-0 flex items-center justify-center opacity-20">
        <svg width="80" height="80" viewBox="0 0 24 24" fill="none" stroke="#1e3a5f" stroke-width="1.5">
          <rect x="3" y="3" width="18" height="18" rx="2"/>
          <circle cx="8.5" cy="8.5" r="1.5"/>
          <path d="m21 15-5-5L5 21"/>
        </svg>
      </div>
      <div class="relative z-10 text-center">
        <div class="text-xs text-slate-600 tracking-widest uppercase font-medium">Chennai, 2015</div>
        <div class="text-xs text-slate-400 mt-1">[ aerial flood photograph ]</div>
      </div>
    </div>
  </div>

</div>


---

# The problem




---
layout: none
background: '#050d1a'
---

<!-- ═══════════════════════════════════════════
     ACT 2 — THE PROBLEM
     Slide: Video left, image right
     Time: 2:00 – 4:00
     ═══════════════════════════════════════════ -->

<div class="w-full h-full flex">

  <!-- Left panel — video -->
  <div class="w-1/2 h-full relative overflow-hidden bg-black">
    <video
      class="w-full h-full object-cover"
      src="/img/12303330_1080_1920_60fps.mp4"
      autoplay
      loop
      muted
      playsinline
    />
  </div>

  <!-- Right panel — image -->
  <div class="w-1/2 h-full relative overflow-hidden bg-slate-900">
    <img
      class="w-full h-full object-cover"
      src="/img/3600.jpg.jxl"
      alt="Chennai flood aerial"
    />
  </div>

</div>

<!--
SPEAKER NOTES — ACT 2 (2:00–4:00)



Now — if you are a city planner in Rotterdam, or Chennai, or anywhere, and you need
to decide whether to build a water square, retrofit green roofs across a district,
or reroute a drainage channel — what tools do you actually reach for?

[RHETORICAL PAUSE — 2 seconds]

There are powerful hydrological models. SFINCS, Delft3D, HEC-RAS. But they require
specialist knowledge to configure and run. Their outputs arrive as large raster files
in formats that most planning offices cannot open. The simulations exist, but they live
behind a wall of technical complexity.

And critically — the participatory dimension is almost entirely absent. The urban planner
who needs to make the decision, the community that will live with the consequences — they
are downstream of the science, not part of it.

There is no shortage of data. There is no shortage of models. What is scarce — what is
almost universally absent — is the layer that connects the two to the people who need to act.

That is the gap this platform is designed to close."

DIRECTOR: The rhetorical question is your key moment. Don't answer it for 2 full seconds.
'The problem is access' — say it like a conclusion, not a transition.
-->

---
layout: none
background: '#ffffff'
---

<!-- ═══════════════════════════════════════════
     ACT 2b — URBAN FLOOD IMPACT
     Slide: Full-page impact card
     ═══════════════════════════════════════════ -->

<FloodImpactCard />

---
layout: center
background: '#050d1a'
---

<!-- ═══════════════════════════════════════════
     ACT 3 — THE PLATFORM (HERO SLIDE)
     Slide: Full-width interface screenshot
     Time: 4:00 – 6:30
     ═══════════════════════════════════════════ -->

<div class="absolute top-0 left-0 right-0 h-0.5 bg-teal-500"></div>

<div class="text-xs text-teal-400 tracking-widest uppercase mb-4 font-medium">
  Planning interface · Rotterdam · 50 mm/h scenario
</div>

<!-- Main interface mockup area — replace with actual screenshot -->
<div class="relative w-full bg-slate-900 border border-slate-700 rounded-xl overflow-hidden"
     style="aspect-ratio: 16/7">

  <!-- Map area placeholder -->
  <div class="absolute inset-0 flex items-center justify-center"
       style="background: repeating-linear-gradient(0deg,rgba(55,138,221,.05) 0,rgba(55,138,221,.05) 1px,transparent 1px,transparent 24px),
              repeating-linear-gradient(90deg,rgba(55,138,221,.05) 0,rgba(55,138,221,.05) 1px,transparent 1px,transparent 24px)">
    <span class="text-slate-700 text-sm italic">[ MapLibre GL flood raster overlay — actual screenshot here ]</span>
  </div>

  <!-- Sidebar -->
  <div class="absolute left-4 top-4 bottom-4 w-36 bg-slate-950 border border-slate-700 rounded-lg p-3">
    <div class="text-xs text-blue-400 font-medium mb-3">Interventions</div>
    <div class="space-y-2">
      <div class="bg-teal-900 border border-teal-700 rounded px-2 py-1.5 text-xs text-teal-300">Green roofs ✓</div>
      <div class="bg-slate-800 rounded px-2 py-1.5 text-xs text-slate-400">Water squares</div>
      <div class="bg-slate-800 rounded px-2 py-1.5 text-xs text-slate-400">Thin dams</div>
      <div class="bg-slate-800 rounded px-2 py-1.5 text-xs text-slate-400">Permeable paving</div>
      <div class="bg-slate-800 rounded px-2 py-1.5 text-xs text-slate-400">Urban parks</div>
    </div>
  </div>

  <!-- Top bar -->
  <div class="absolute top-4 right-4 flex items-center gap-2">
    <div class="bg-slate-950 border border-slate-700 rounded px-3 py-1.5 text-xs text-blue-400 font-medium">50 mm/h</div>
    <div class="bg-slate-950 border border-teal-700 rounded px-3 py-1.5 text-xs text-teal-400">Scenario A</div>
  </div>

  <!-- Damage metric -->
  <div class="absolute bottom-4 right-4 bg-slate-950 border border-slate-700 rounded-lg p-3 text-right">
    <div class="text-xs text-slate-500 mb-1">Damage reduction</div>
    <div class="text-2xl font-medium text-teal-400">−31%</div>
    <div class="text-xs text-slate-600 mt-1">after intervention</div>
  </div>

  <!-- Callout labels -->
  <div class="absolute bottom-4 left-44 bg-slate-950 border border-slate-700 rounded px-3 py-1.5">
    <div class="flex items-center gap-3">
      <div class="w-12 h-1.5 rounded" style="background: linear-gradient(90deg, #1e3a5f, #378add, #93c5fd)"></div>
      <span class="text-xs text-slate-500">0 m → 2 m depth</span>
    </div>
  </div>
</div>

<div class="mt-3 text-xs text-slate-600 italic">
  Rotterdam · 50 mm/h rainfall · green roof intervention drawn · water depth output
</div>

<!--
SPEAKER NOTES — ACT 3 (4:00–6:30)

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
layout: center
background: '#050d1a'
---

<!-- ═══════════════════════════════════════════
     ACT 4 — HOW IT WORKS
     Slide: Pipeline + service layer
     Time: 6:30 – 8:30
     ═══════════════════════════════════════════ -->

<div class="absolute top-0 left-0 right-0 h-0.5 bg-blue-500"></div>

<div class="text-xs text-blue-400 tracking-widest uppercase mb-6 font-medium">
  Simulation pipeline
</div>

<!-- Three-stage pipeline -->
<div class="flex items-center gap-0 mb-8 w-full">
  <div class="flex-1 bg-slate-900 border border-slate-700 rounded-xl p-5 text-center">
    <div class="text-xs text-blue-400 font-medium mb-3 uppercase tracking-wide">Input</div>
    <div class="text-sm text-slate-400 leading-relaxed">
      Rainfall scenario<br/>
      City geometry (GIS)<br/>
      Intervention polygons
    </div>
  </div>
  <div class="text-slate-600 text-2xl px-4">→</div>
  <div class="flex-1 bg-slate-900 border border-blue-800 rounded-xl p-5 text-center">
    <div class="text-xs text-blue-400 font-medium mb-3 uppercase tracking-wide">SFINCS model</div>
    <div class="text-sm text-slate-400 leading-relaxed">
      Shallow water equations<br/>
      High-resolution grid<br/>
      Hydrodynamic routing
    </div>
  </div>
  <div class="text-slate-600 text-2xl px-4">→</div>
  <div class="flex-1 bg-slate-900 border border-slate-700 rounded-xl p-5 text-center">
    <div class="text-xs text-teal-400 font-medium mb-3 uppercase tracking-wide">Output</div>
    <div class="text-sm text-slate-400 leading-relaxed">
      Water depth (m)<br/>
      Flow velocity (m/s)<br/>
      Economic damage (€)
    </div>
  </div>
</div>

<div class="w-full h-px bg-slate-800 mb-6"></div>

<div class="text-xs text-slate-600 uppercase tracking-widest mb-3">Service layer</div>

<!-- Service row -->
<div class="flex items-center gap-0 w-full">
  <div class="flex-1 bg-slate-950 border border-slate-800 rounded-lg py-3 px-2 text-center">
    <div class="text-xs text-purple-400 font-medium">SvelteKit</div>
    <div class="text-xs text-slate-600 mt-1">Frontend</div>
  </div>
  <div class="text-slate-700 px-2">→</div>
  <div class="flex-1 bg-slate-950 border border-slate-800 rounded-lg py-3 px-2 text-center">
    <div class="text-xs text-teal-400 font-medium">Django</div>
    <div class="text-xs text-slate-600 mt-1">REST API</div>
  </div>
  <div class="text-slate-700 px-2">→</div>
  <div class="flex-1 bg-slate-950 border border-slate-800 rounded-lg py-3 px-2 text-center">
    <div class="text-xs text-blue-400 font-medium">TiTiler</div>
    <div class="text-xs text-slate-600 mt-1">Raster tiles</div>
  </div>
  <div class="text-slate-700 px-2">→</div>
  <div class="flex-1 bg-slate-950 border border-slate-800 rounded-lg py-3 px-2 text-center">
    <div class="text-xs text-amber-400 font-medium">PostgreSQL</div>
    <div class="text-xs text-slate-600 mt-1">+PostGIS</div>
  </div>
  <div class="text-slate-700 px-2">→</div>
  <div class="flex-1 bg-slate-950 border border-slate-800 rounded-lg py-3 px-2 text-center">
    <div class="text-xs text-slate-400 font-medium">Docker</div>
    <div class="text-xs text-slate-600 mt-1">SURF Cloud</div>
  </div>
</div>

<!--
SPEAKER NOTES — ACT 4 (6:30–8:30)

"Let me briefly open the hood.

At the core is the SFINCS hydrodynamic model — Super-Fast Inundation of CoastS.
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
layout: center
background: '#050d1a'
---

<!-- ═══════════════════════════════════════════
     ACT 5 — TWO CITIES
     Slide: Split Rotterdam / Chennai panels
     Time: 8:30 – 10:30
     ═══════════════════════════════════════════ -->

<div class="grid grid-cols-2 gap-0 w-full h-full" style="min-height: 340px">

  <!-- Rotterdam -->
  <div class="flex flex-col justify-center px-10 py-8 border-r border-slate-800 relative">
    <div class="absolute top-0 left-0 right-0 h-0.5 bg-blue-500"></div>
    <div class="text-xs text-blue-400 tracking-widest uppercase mb-2 font-medium">
      Rotterdam, Netherlands
    </div>
    <h3 class="text-2xl font-medium text-white mb-4">River delta city</h3>
    <div class="w-5 h-px bg-slate-700 mb-4"></div>
    <ul class="space-y-2">
      <li class="flex items-center gap-2 text-sm text-slate-400">
        <span class="w-1.5 h-1.5 rounded-full bg-blue-500 flex-shrink-0"></span>
        Dense urban morphology
      </li>
      <li class="flex items-center gap-2 text-sm text-slate-400">
        <span class="w-1.5 h-1.5 rounded-full bg-blue-500 flex-shrink-0"></span>
        Return periods: 10–100 yr
      </li>
      <li class="flex items-center gap-2 text-sm text-slate-400">
        <span class="w-1.5 h-1.5 rounded-full bg-blue-500 flex-shrink-0"></span>
        PDOK/CBS neighbourhood data
      </li>
      <li class="flex items-center gap-2 text-sm text-slate-400">
        <span class="w-1.5 h-1.5 rounded-full bg-blue-500 flex-shrink-0"></span>
        Advanced water management legacy
      </li>
    </ul>
  </div>

  <!-- Same platform divider + Chennai -->
  <div class="flex flex-col justify-center px-10 py-8 relative">
    <div class="absolute top-0 left-0 right-0 h-0.5 bg-amber-500"></div>
    <div class="text-xs text-amber-500 tracking-widest uppercase mb-2 font-medium">
      Chennai (Tambaram), India
    </div>
    <h3 class="text-2xl font-medium text-white mb-4">Monsoon coast city</h3>
    <div class="w-5 h-px bg-slate-700 mb-4"></div>
    <ul class="space-y-2">
      <li class="flex items-center gap-2 text-sm text-slate-400">
        <span class="w-1.5 h-1.5 rounded-full bg-amber-500 flex-shrink-0"></span>
        Rapid urban expansion
      </li>
      <li class="flex items-center gap-2 text-sm text-slate-400">
        <span class="w-1.5 h-1.5 rounded-full bg-amber-500 flex-shrink-0"></span>
        Intensities: 10–100 mm/h
      </li>
      <li class="flex items-center gap-2 text-sm text-slate-400">
        <span class="w-1.5 h-1.5 rounded-full bg-amber-500 flex-shrink-0"></span>
        Limited drainage infrastructure
      </li>
      <li class="flex items-center gap-2 text-sm text-slate-400">
        <span class="w-1.5 h-1.5 rounded-full bg-amber-500 flex-shrink-0"></span>
        Custom catchment delineation
      </li>
    </ul>
  </div>

</div>

<div class="mt-4 text-center text-xs text-slate-600 italic">
  Same platform · same ontology · same pipeline · different worlds
</div>

<!--
SPEAKER NOTES — ACT 5 (8:30–10:30)

"One city is a prototype. Two cities with fundamentally different flood regimes,
different data infrastructures, and different planning contexts — that is a
demonstration of generalisability.

Rotterdam is a river delta city. Dense urban morphology, sophisticated water management
legacy, well-structured spatial data from PDOK and CBS, rainfall return periods from
10 to 100 years. This is where the platform was designed and initially calibrated.

Chennai — specifically the Tambaram area — is a monsoon coast city. Rapid urban expansion,
limited drainage infrastructure, a very different data landscape, and rainfall intensities
modelled at 10 to 100 millimetres per hour. This is a context where the consequences
of flooding are more severe and the planning resources are more constrained.

Same platform. Same ontology. Same simulation pipeline. Different cities, different
flood regimes, different spatial datasets — and the architecture holds across both.

What this demonstrates is not just that the platform works in two cities. It demonstrates
that the design decisions we made — the ontology-driven data model, the COG raster pipeline,
the city-agnostic intervention type system — were the right ones.

Scalability and interoperability are not aspirational here. They are demonstrated properties."

DIRECTOR: 'Same platform. Same ontology.' — three short sentences, each a beat, then pause.
The final line is your act close — slow, deliberate, earned.
-->

---
layout: center
background: '#050d1a'
---

<!-- ═══════════════════════════════════════════
     ACT 6 — THE CLOSE
     Slide: Four contribution cards + closing statement
     Time: 10:30 – 13:00
     ═══════════════════════════════════════════ -->

<div class="absolute top-0 left-0 right-0 h-0.5 bg-slate-600"></div>

<div class="text-xs text-slate-500 tracking-widest uppercase mb-5 font-medium">
  Research contributions
</div>

<div class="grid grid-cols-2 gap-3 mb-5">
  <div class="bg-slate-900 border border-slate-700 rounded-xl p-5 text-left">
    <div class="text-xs text-blue-400 font-medium mb-2 uppercase tracking-wider">01 — Participatory twin</div>
    <div class="text-base font-medium text-white mb-2 leading-snug">The model is no longer behind a wall</div>
    <p class="text-sm text-slate-500 leading-relaxed">
      Non-expert stakeholders can co-design flood interventions directly.
      Bridges hydrology and urban governance.
    </p>
  </div>
  <div class="bg-slate-900 border border-slate-700 rounded-xl p-5 text-left">
    <div class="text-xs text-teal-400 font-medium mb-2 uppercase tracking-wider">02 — Semantic layer</div>
    <div class="text-base font-medium text-white mb-2 leading-snug">The platform speaks to the world</div>
    <p class="text-sm text-slate-500 leading-relaxed">
      OWL ontology enables linked data integration with GIS, BIM, and climate systems.
      No custom glue code per city.
    </p>
  </div>
  <div class="bg-slate-900 border border-slate-700 rounded-xl p-5 text-left">
    <div class="text-xs text-amber-400 font-medium mb-2 uppercase tracking-wider">03 — Raster streaming</div>
    <div class="text-base font-medium text-white mb-2 leading-snug">City-wide data in the browser, instantly</div>
    <p class="text-sm text-slate-500 leading-relaxed">
      COG + TiTiler delivers large simulation outputs at sub-second tile rendering.
      No pre-tiling or data duplication.
    </p>
  </div>
  <div class="bg-slate-900 border border-slate-700 rounded-xl p-5 text-left">
    <div class="text-xs text-purple-400 font-medium mb-2 uppercase tracking-wider">04 — Resilience scoring</div>
    <div class="text-base font-medium text-white mb-2 leading-snug">Evidence replaces intuition</div>
    <p class="text-sm text-slate-500 leading-relaxed">
      Quantitative before/after at neighbourhood scale across depth,
      velocity and economic damage.
    </p>
  </div>
</div>

<div class="border-t border-slate-800 pt-4 flex items-center justify-between">
  <p class="text-sm text-slate-300 italic text-left max-w-xl">
    Cities are going to flood more. The question is whether the people responsible
    have tools that match the scale of the problem.
  </p>
  <div class="text-xs text-slate-600 text-right flex-shrink-0 ml-8">
    resilienthydrotwin<br/>
    open source · rhdt.ttl
  </div>
</div>

<!--
SPEAKER NOTES — ACT 6 (10:30–13:00)

"Let me close by being precise about what this research contributes — because I think
there are four things here, and they operate at different levels.

First: a participatory digital twin architecture. We have extended traditional hydrological
simulation with an interactive, web-based planning layer. The model is no longer behind a wall.
Non-expert stakeholders — planners, community representatives, decision-makers — can now
co-design flood interventions without specialist training.

Second: semantic interoperability through a formal OWL ontology. Every concept in the platform
— every intervention type, every scenario variable, every simulation output — is a typed,
formally defined class. This means the platform connects to GIS systems, BIM tools, and
climate datasets without custom integration work per deployment. It is designed to grow.

Third: a real-time raster streaming architecture using Cloud-Optimized GeoTIFFs and TiTiler.
This delivers large-scale simulation outputs — city-wide, high-resolution rasters — to a
standard browser at sub-second tile rendering. No pre-processing pipeline. No data duplication.
This is a non-trivial engineering contribution for anyone working with large geospatial
simulation outputs.

And fourth: a comparative resilience scoring system. Quantitative before-and-after assessment
at neighbourhood and district scale, across water depth, flow velocity, and economic damage.
For the first time, planners can ask which intervention, in which district, reduces damage
most per euro spent — and get a spatially explicit, evidence-based answer.

[PAUSE — 2 full seconds]

Cities are going to flood more. That is not a prediction — it is already happening.
The question is whether the people responsible for those cities have tools that match
the scale of that problem.

Resilient Hydro Twin is our answer to that question.

Thank you."

DIRECTOR: Four contributions — measured pace, no rushing. After the fourth, pause fully.
The closing two sentences echo Act 1. Say them slowly. 'Thank you.' Full stop.
Do NOT say 'any questions' or 'so yes, that's it'. Let the MC take over.
-->

---
layout: cover
background: '#050d1a'
---

<!-- ═══════════════════════════════════════════
     CLOSING / Q&A SLIDE
     Stays on screen during questions
     ═══════════════════════════════════════════ -->

<div class="absolute top-0 left-0 right-0 h-0.5 bg-blue-500"></div>

<div class="flex flex-col items-start text-left px-16 h-full justify-center">
  <div class="text-xs text-blue-400 tracking-widest uppercase mb-3 font-medium">
    Questions & Discussion
  </div>
  <h1 class="text-4xl font-medium text-white leading-tight mb-4">
    Resilient Hydro Twin
  </h1>
  <p class="text-slate-400 text-base leading-relaxed mb-8">
    Participatory Digital Twin for Urban Flood Resilience<br/>
    Rotterdam · Chennai · Open Source
  </p>
  <div class="grid grid-cols-2 gap-3 text-sm w-full max-w-lg">
    <div class="bg-slate-900 border border-slate-700 rounded-lg p-3">
      <div class="text-xs text-slate-500 mb-1">01</div>
      <div class="text-white text-xs">The model is no longer behind a wall</div>
    </div>
    <div class="bg-slate-900 border border-slate-700 rounded-lg p-3">
      <div class="text-xs text-slate-500 mb-1">02</div>
      <div class="text-white text-xs">The platform speaks to the world</div>
    </div>
    <div class="bg-slate-900 border border-slate-700 rounded-lg p-3">
      <div class="text-xs text-slate-500 mb-1">03</div>
      <div class="text-white text-xs">City-wide data in the browser, instantly</div>
    </div>
    <div class="bg-slate-900 border border-slate-700 rounded-lg p-3">
      <div class="text-xs text-slate-500 mb-1">04</div>
      <div class="text-white text-xs">Evidence replaces intuition</div>
    </div>
  </div>
  <div class="mt-8 text-xs text-slate-600">
    Özgün Balaban · TU Delft · 2026 · github: resilienthydrotwin
  </div>
</div>

<!--
This slide stays on screen for the entire Q&A.
Anyone who arrives late, zones out, or wants to find the paper later
can get everything they need from this slide alone.
Key takeaways visible. Name and GitHub handle bottom left.
-->