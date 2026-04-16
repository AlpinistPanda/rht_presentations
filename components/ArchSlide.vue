<template>
  <div class="w-full h-full flex flex-col justify-center px-6 py-2 font-sans text-gray-900 select-none">

    <!-- ── Title row ── -->
    <p class="text-[10px] uppercase tracking-[0.16em] text-gray-400 mb-2 font-semibold">System Architecture</p>

    <!-- ══════════════════════════════════════════════════════
         TOP ROW — External models & data sources
    ═══════════════════════════════════════════════════════════ -->
    <div class="flex gap-2 w-full mb-1">

      <!-- Section label: Simulation Models -->
      <div class="ext-section" style="flex:1.8;">
        <p class="ext-section-label text-rose-500">Simulation Models</p>
        <div class="flex gap-1.5">

          <!-- MIKE+ -->
          <div class="ext-box theme-mike" style="flex:1;">
            <div class="flex items-center gap-1 mb-0.5">
              <span class="icon-badge bg-red-100 text-red-700">M+</span>
              <span class="ext-name text-red-700">MIKE+</span>
              <span class="city-tag tag-india">Chennai</span>
            </div>
            <div class="ext-detail">DHI 2D urban drainage &amp; overland flood</div>
            <div class="flex flex-wrap gap-0.5 mt-0.5">
              <span class="badge badge-red">Monsoon</span>
              <span class="badge badge-red">Pipe network</span>
            </div>
          </div>

          <!-- SFINCS -->
          <div class="ext-box theme-sfincs" style="flex:1;">
            <div class="flex items-center gap-1 mb-0.5">
              <span class="icon-badge bg-blue-100 text-blue-700">SF</span>
              <span class="ext-name text-blue-700">SFINCS</span>
              <span class="city-tag tag-nl">Rotterdam</span>
            </div>
            <div class="ext-detail">Super-Fast INundation of CoastS — shallow water</div>
            <div class="flex flex-wrap gap-0.5 mt-0.5">
              <span class="badge badge-blue">Coastal surge</span>
              <span class="badge badge-blue">10–100 yr RP</span>
            </div>
          </div>

          <!-- Delft-FIAT -->
          <div class="ext-box theme-fiat" style="flex:1;">
            <div class="flex items-center gap-1 mb-0.5">
              <span class="icon-badge bg-indigo-100 text-indigo-700">DF</span>
              <span class="ext-name text-indigo-700">Delft-FIAT</span>
              <span class="city-tag tag-nl">Rotterdam</span>
            </div>
            <div class="ext-detail">Flood Impact Assessment Tool — damage model</div>
            <div class="flex flex-wrap gap-0.5 mt-0.5">
              <span class="badge badge-indigo">Damage curves</span>
              <span class="badge badge-indigo">€ output</span>
            </div>
          </div>

          <!-- SUMO -->
          <div class="ext-box theme-sumo" style="flex:1;">
            <div class="flex items-center gap-1 mb-0.5">
              <span class="icon-badge bg-amber-100 text-amber-700">SU</span>
              <span class="ext-name text-amber-700">SUMO</span>
              <span class="city-tag tag-both">Multi-city</span>
            </div>
            <div class="ext-detail">Urban Mobility — microscopic traffic &amp; evacuation</div>
            <div class="flex flex-wrap gap-0.5 mt-0.5">
              <span class="badge badge-amber">Road network</span>
              <span class="badge badge-amber">Evacuation</span>
            </div>
          </div>

        </div>
      </div>

      <!-- Section label: Data Sources -->
      <div class="ext-section" style="flex:1.6;">
        <p class="ext-section-label text-emerald-600">Data Sources</p>
        <div class="flex gap-1.5">

          <!-- PDOK -->
          <div class="ext-box theme-pdok" style="flex:1;">
            <div class="flex items-center gap-1 mb-0.5">
              <span class="icon-badge bg-emerald-100 text-emerald-700">PD</span>
              <span class="ext-name text-emerald-700">PDOK</span>
              <span class="city-tag tag-nl">NL</span>
            </div>
            <div class="ext-detail">National geo-registry — buildings, DEM, topography</div>
            <div class="flex flex-wrap gap-0.5 mt-0.5">
              <span class="badge badge-teal">BAG</span>
              <span class="badge badge-teal">AHN3 DEM</span>
              <span class="badge badge-teal">BGT</span>
            </div>
          </div>

          <!-- CBS -->
          <div class="ext-box theme-cbs" style="flex:1;">
            <div class="flex items-center gap-1 mb-0.5">
              <span class="icon-badge bg-cyan-100 text-cyan-700">CB</span>
              <span class="ext-name text-cyan-700">CBS</span>
              <span class="city-tag tag-nl">NL</span>
            </div>
            <div class="ext-detail">Statistics Netherlands — neighbourhood socioeconomics</div>
            <div class="flex flex-wrap gap-0.5 mt-0.5">
              <span class="badge badge-cyan">Buurt grid</span>
              <span class="badge badge-cyan">Population</span>
            </div>
          </div>

          <!-- OSM / IMD -->
          <div class="ext-box theme-osm" style="flex:1;">
            <div class="flex items-center gap-1 mb-0.5">
              <span class="icon-badge bg-orange-100 text-orange-700">OS</span>
              <span class="ext-name text-orange-700">OSM / IMD</span>
              <span class="city-tag tag-both">Global</span>
            </div>
            <div class="ext-detail">Road network, land use, buildings &amp; rainfall data</div>
            <div class="flex flex-wrap gap-0.5 mt-0.5">
              <span class="badge badge-orange">Road graph</span>
              <span class="badge badge-orange">Rainfall</span>
            </div>
          </div>

        </div>
      </div>

    </div>

    <!-- ── Downward arrows from external row into pipeline ── -->
    <div class="flex justify-end pr-1 mb-1">
      <div class="flex items-center gap-1" style="width: calc(1.6 / 3.4 * 100%);">
        <div class="down-trunk"/>
        <span class="down-label">COG rasters · GeoJSON · scenario metadata</span>
      </div>
    </div>

    <!-- ══════════════════════════════════════════════════════
         MAIN PIPELINE — same as before
    ═══════════════════════════════════════════════════════════ -->
    <div class="flex items-stretch gap-0 w-full">

      <!-- ① Users -->
      <div class="arch-box theme-user" style="min-width:100px; flex:1.1;">
        <span class="box-tier">Client Layer</span>
        <span class="box-name text-blue-700">User Browsers</span>
        <div class="mt-1 flex flex-col gap-1">
          <div class="mini">
            <strong class="mini-title">Researchers &amp; Planners</strong>
            Flood planning, interventions, 3D viewer
          </div>
          <div class="mini">
            <strong class="mini-title">Administrators</strong>
            Approve users, manage scenarios
          </div>
        </div>
      </div>

      <!-- → HTTP :80 -->
      <div class="arrow-seg">
        <div class="arrow-line"/>
        <span class="arrow-tag">HTTP :80</span>
        <div class="arrowhead"/>
      </div>

      <!-- ② NGINX -->
      <div class="arch-box theme-proxy" style="min-width:120px; flex:1.4;">
        <span class="box-tier">Reverse Proxy</span>
        <span class="box-name text-indigo-700">NGINX (Alpine)</span>
        <div class="mt-1 flex flex-col gap-1">
          <div class="mini"><strong class="mini-title">/* → :3000</strong>SvelteKit SPA</div>
          <div class="mini"><strong class="mini-title">/api/* → :8000</strong>Django REST API</div>
          <div class="mini"><strong class="mini-title">/tiles/* → :8080</strong>Titiler tile server</div>
        </div>
        <div class="mt-1 flex flex-wrap gap-1">
          <span class="badge badge-purple">TLS</span>
          <span class="badge badge-blue">Static files</span>
        </div>
      </div>

      <!-- → split -->
      <div class="arrow-seg split-arrow">
        <div class="split-lines">
          <div class="split-line top"/>
          <div class="split-line mid"/>
          <div class="split-line bot"/>
        </div>
        <div class="split-tags">
          <span class="arrow-tag cyan">:3000</span>
          <span class="arrow-tag green">:8000</span>
          <span class="arrow-tag amber">:8080</span>
        </div>
      </div>

      <!-- ③ Services column (stacked) -->
      <div class="flex flex-col gap-1" style="flex:1.8; min-width:150px;">

        <div class="arch-box theme-fe flex-1">
          <span class="box-tier">Frontend Service</span>
          <span class="box-name text-cyan-700">SvelteKit 2 + Svelte 5</span>
          <div class="box-detail mt-0.5">Maplibre GL · Cesium 3D · JWT auth</div>
          <div class="flex flex-wrap gap-1 mt-0.5">
            <span class="badge badge-cyan">TypeScript</span>
            <span class="badge badge-cyan">Tailwind</span>
          </div>
        </div>

        <div class="arch-box theme-be flex-1">
          <span class="box-tier">Backend API</span>
          <span class="box-name text-green-700">Django 5 + DRF</span>
          <div class="box-detail mt-0.5">/scenarios · /interventions · /rasters · Gunicorn</div>
          <div class="flex flex-wrap gap-1 mt-0.5">
            <span class="badge badge-green">Python 3.12</span>
            <span class="badge badge-green">GeoJSON</span>
          </div>
        </div>

        <div class="arch-box theme-tile flex-1">
          <span class="box-tier">Tile Server</span>
          <span class="box-name text-amber-700">Titiler (OGC)</span>
          <div class="box-detail mt-0.5">COG → XYZ/WMTS raster tiles · rasterio</div>
          <div class="flex flex-wrap gap-1 mt-0.5">
            <span class="badge badge-orange">COG</span>
            <span class="badge badge-orange">rasterio</span>
          </div>
        </div>

      </div>

      <!-- → to data layer -->
      <div class="arrow-seg split-arrow">
        <div class="split-lines two">
          <div class="split-line top-2"/>
          <div class="split-line bot-2"/>
        </div>
        <div class="split-tags two-tags">
          <span class="arrow-tag purple">SQL :5432</span>
          <span class="arrow-tag teal">reads</span>
        </div>
      </div>

      <!-- ④ Data layer column (stacked) -->
      <div class="flex flex-col gap-1" style="flex:1.6; min-width:140px;">

        <div class="arch-box theme-db flex-1">
          <span class="box-tier">Database</span>
          <span class="box-name text-purple-700">PostgreSQL 16</span>
          <div class="box-detail mt-0.5">scenario · intervention · aggregation_area · log_entry</div>
          <div class="flex flex-wrap gap-1 mt-0.5">
            <span class="badge badge-purple">Volume: postgres_data</span>
          </div>
        </div>

        <div class="arch-box theme-data flex-1">
          <span class="box-tier">Geospatial Data Store</span>
          <span class="box-name text-emerald-700">COG Raster Files</span>
          <div class="box-detail mt-0.5">Flood depth · Rotterdam · Chennai · Tambaram</div>
          <div class="flex flex-wrap gap-1 mt-0.5">
            <span class="badge badge-teal">GeoTIFF / COG</span>
          </div>
        </div>

      </div>

    </div>

    <!-- ── Legend ── -->
    <div class="flex gap-3 mt-2 flex-wrap">
      <div v-for="l in legend" :key="l.label" class="flex items-center gap-1.5">
        <div class="w-2 h-2 rounded-full flex-shrink-0" :style="{ background: l.color }"/>
        <span class="text-[9px] uppercase tracking-wider text-gray-400">{{ l.label }}</span>
      </div>
    </div>

  </div>
</template>

<script setup>
const legend = [
  { label: 'MIKE+ / SFINCS / Delft-FIAT', color: '#ef4444' },
  { label: 'SUMO Traffic',                 color: '#f59e0b' },
  { label: 'PDOK / CBS / OSM',             color: '#10b981' },
  { label: 'Frontend',                     color: '#06b6d4' },
  { label: 'Backend API',                  color: '#22c55e' },
  { label: 'Tile Server',                  color: '#f59e0b' },
  { label: 'Database',                     color: '#a855f7' },
  { label: 'Raster Data',                  color: '#10b981' },
  { label: 'Reverse Proxy',                color: '#6366f1' },
]
</script>

<style scoped>
/* ── External top row ── */
.ext-section {
  display: flex;
  flex-direction: column;
}
.ext-section-label {
  font-size: 0.52rem;
  font-weight: 800;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  margin-bottom: 3px;
}

.ext-box {
  border-radius: 6px;
  padding: 5px 7px;
  display: flex;
  flex-direction: column;
  border-width: 1px;
  border-style: solid;
}

.theme-mike    { background: #fee2e2; border-color: #ef4444; }
.theme-sfincs  { background: #dbeafe; border-color: #3b82f6; }
.theme-fiat    { background: #e0e7ff; border-color: #6366f1; }
.theme-sumo    { background: #fef3c7; border-color: #f59e0b; }
.theme-pdok    { background: #d1fae5; border-color: #10b981; }
.theme-cbs     { background: #cffafe; border-color: #06b6d4; }
.theme-osm     { background: #ffedd5; border-color: #f97316; }

.icon-badge {
  width: 18px;
  height: 18px;
  border-radius: 4px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.42rem;
  font-weight: 800;
  flex-shrink: 0;
}

.ext-name {
  font-size: 0.65rem;
  font-weight: 700;
  line-height: 1.2;
}

.ext-detail {
  font-size: 0.5rem;
  color: #475569;
  line-height: 1.3;
}

/* ── City tags ── */
.city-tag {
  display: inline-block;
  padding: 0px 4px;
  border-radius: 999px;
  font-size: 0.42rem;
  font-weight: 700;
  letter-spacing: 0.03em;
  vertical-align: middle;
  margin-left: 2px;
}
.tag-india { background: #fde68a; color: #92400e; }
.tag-nl    { background: #bfdbfe; color: #1e40af; }
.tag-both  { background: #e9d5ff; color: #6b21a8; }

/* ── Downward connector ── */
.down-trunk {
  width: 1.5px;
  height: 10px;
  background: #94a3b8;
  flex-shrink: 0;
}
.down-label {
  font-size: 0.44rem;
  color: #64748b;
  letter-spacing: 0.03em;
  white-space: nowrap;
}

/* ── Box base (main pipeline) ── */
.arch-box {
  border-radius: 8px;
  padding: 7px 9px;
  display: flex;
  flex-direction: column;
  border-width: 1px;
  border-style: solid;
}

.theme-user  { background: #dbeafe; border-color: #3b82f6; }
.theme-proxy { background: #e0e7ff; border-color: #6366f1; }
.theme-fe    { background: #cffafe; border-color: #06b6d4; }
.theme-be    { background: #dcfce7; border-color: #22c55e; }
.theme-tile  { background: #fef3c7; border-color: #f59e0b; }
.theme-db    { background: #f3e8ff; border-color: #a855f7; }
.theme-data  { background: #d1fae5; border-color: #10b981; }

.box-tier {
  font-size: 0.5rem;
  font-weight: 700;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: #64748b;
  margin-bottom: 1px;
}
.box-name {
  font-size: 0.68rem;
  font-weight: 700;
  line-height: 1.2;
}
.box-detail {
  font-size: 0.55rem;
  color: #475569;
  line-height: 1.4;
}
.mini {
  background: rgba(0,0,0,0.05);
  border-radius: 4px;
  padding: 3px 5px;
  font-size: 0.52rem;
  line-height: 1.4;
  color: #334155;
  border: 1px solid rgba(0,0,0,0.06);
}
.mini-title {
  display: block;
  font-weight: 700;
  font-size: 0.54rem;
  margin-bottom: 1px;
}

/* ── Badges ── */
.badge {
  display: inline-block;
  padding: 1px 5px;
  border-radius: 999px;
  font-size: 0.46rem;
  font-weight: 600;
}
.badge-red    { background: #fecaca; color: #991b1b; }
.badge-blue   { background: #bfdbfe; color: #1d4ed8; }
.badge-indigo { background: #c7d2fe; color: #3730a3; }
.badge-amber  { background: #fde68a; color: #92400e; }
.badge-teal   { background: #a7f3d0; color: #065f46; }
.badge-cyan   { background: #a5f3fc; color: #0e7490; }
.badge-orange { background: #fed7aa; color: #b45309; }
.badge-blue   { background: #bfdbfe; color: #1d4ed8; }
.badge-purple { background: #e9d5ff; color: #7e22ce; }
.badge-green  { background: #bbf7d0; color: #15803d; }

/* ── Arrows ── */
.arrow-seg {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 0 5px;
  flex-shrink: 0;
  position: relative;
  min-width: 48px;
}
.arrow-line {
  width: 100%;
  height: 1.5px;
  background: #94a3b8;
}
.arrowhead {
  width: 0;
  height: 0;
  border-top: 4px solid transparent;
  border-bottom: 4px solid transparent;
  border-left: 6px solid #94a3b8;
  margin-top: -1px;
  align-self: flex-end;
}
.arrow-tag {
  font-size: 0.46rem;
  letter-spacing: 0.06em;
  color: #64748b;
  white-space: nowrap;
  margin: 2px 0;
}
.arrow-tag.cyan   { color: #0e7490; }
.arrow-tag.green  { color: #15803d; }
.arrow-tag.amber  { color: #b45309; }
.arrow-tag.purple { color: #7e22ce; }
.arrow-tag.teal   { color: #065f46; }

/* ── Split arrows (3-way) ── */
.split-arrow {
  flex-direction: row;
  gap: 4px;
}
.split-lines {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-self: stretch;
  gap: 0;
  width: 18px;
  position: relative;
}
.split-lines::before {
  content: '';
  position: absolute;
  left: 0;
  top: 16%;
  height: 68%;
  width: 1.5px;
  background: #94a3b8;
}
.split-line {
  height: 1.5px;
  background: #94a3b8;
  width: 100%;
}
.split-lines.two::before { top: 25%; height: 50%; }

.split-tags {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-self: stretch;
}
.two-tags { justify-content: space-evenly; }
</style>
