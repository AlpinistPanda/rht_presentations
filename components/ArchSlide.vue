<template>
  <div class="w-full h-full flex flex-col justify-center px-6 py-3 font-sans text-gray-900 select-none">

    <!-- ── Title row ── -->
    <p class="text-[10px] uppercase tracking-[0.16em] text-gray-400 mb-3 font-semibold">System Architecture</p>

    <!-- ── Main horizontal pipeline ── -->
    <div class="flex items-stretch gap-0 w-full">

      <!-- ① Users -->
      <div class="arch-box theme-user" style="min-width:110px; flex:1.1;">
        <span class="box-tier">Client Layer</span>
        <span class="box-name text-blue-700">User Browsers</span>
        <div class="mt-1.5 flex flex-col gap-1">
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
      <div class="arch-box theme-proxy" style="min-width:130px; flex:1.4;">
        <span class="box-tier">Reverse Proxy</span>
        <span class="box-name text-indigo-700">NGINX (Alpine)</span>
        <div class="mt-1.5 flex flex-col gap-1">
          <div class="mini"><strong class="mini-title">/* → :3000</strong>SvelteKit SPA</div>
          <div class="mini"><strong class="mini-title">/api/* → :8000</strong>Django REST API</div>
          <div class="mini"><strong class="mini-title">/tiles/* → :8080</strong>Titiler tile server</div>
        </div>
        <div class="mt-1.5 flex flex-wrap gap-1">
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
      <div class="flex flex-col gap-1.5" style="flex:1.8; min-width:150px;">

        <div class="arch-box theme-fe flex-1">
          <span class="box-tier">Frontend Service</span>
          <span class="box-name text-cyan-700">SvelteKit 2 + Svelte 5</span>
          <div class="box-detail mt-0.5">Maplibre GL · Cesium 3D · JWT auth</div>
          <div class="flex flex-wrap gap-1 mt-1">
            <span class="badge badge-cyan">TypeScript</span>
            <span class="badge badge-cyan">Tailwind</span>
          </div>
        </div>

        <div class="arch-box theme-be flex-1">
          <span class="box-tier">Backend API</span>
          <span class="box-name text-green-700">Django 5 + DRF</span>
          <div class="box-detail mt-0.5">/scenarios · /interventions · /rasters · Gunicorn</div>
          <div class="flex flex-wrap gap-1 mt-1">
            <span class="badge badge-green">Python 3.12</span>
            <span class="badge badge-green">GeoJSON</span>
          </div>
        </div>

        <div class="arch-box theme-tile flex-1">
          <span class="box-tier">Tile Server</span>
          <span class="box-name text-amber-700">Titiler (OGC)</span>
          <div class="box-detail mt-0.5">COG → XYZ/WMTS raster tiles · rasterio</div>
          <div class="flex flex-wrap gap-1 mt-1">
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
      <div class="flex flex-col gap-1.5" style="flex:1.6; min-width:140px;">

        <div class="arch-box theme-db flex-1">
          <span class="box-tier">Database</span>
          <span class="box-name text-purple-700">PostgreSQL 16</span>
          <div class="box-detail mt-0.5">scenario · intervention · aggregation_area · log_entry</div>
          <div class="flex flex-wrap gap-1 mt-1">
            <span class="badge badge-purple">Volume: postgres_data</span>
          </div>
        </div>

        <div class="arch-box theme-data flex-1">
          <span class="box-tier">Geospatial Data Store</span>
          <span class="box-name text-emerald-700">COG Raster Files</span>
          <div class="box-detail mt-0.5">Flood depth · Rotterdam · Chennai · Tambaram</div>
          <div class="flex flex-wrap gap-1 mt-1">
            <span class="badge badge-teal">GeoTIFF / COG</span>
          </div>
        </div>

      </div>

    </div>

    <!-- ── Legend ── -->
    <div class="flex gap-4 mt-3 flex-wrap">
      <div v-for="l in legend" :key="l.label" class="flex items-center gap-1.5">
        <div class="w-2 h-2 rounded-full flex-shrink-0" :style="{ background: l.color }"/>
        <span class="text-[9px] uppercase tracking-wider text-gray-400">{{ l.label }}</span>
      </div>
    </div>

  </div>
</template>

<script setup>
const legend = [
  { label: 'Frontend',      color: '#06b6d4' },
  { label: 'Backend API',   color: '#22c55e' },
  { label: 'Tile Server',   color: '#f59e0b' },
  { label: 'Database',      color: '#a855f7' },
  { label: 'Raster Data',   color: '#10b981' },
  { label: 'Reverse Proxy', color: '#6366f1' },
]
</script>

<style scoped>
/* ── Box base ── */
.arch-box {
  border-radius: 8px;
  padding: 8px 10px;
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
  font-size: 0.72rem;
  font-weight: 700;
  line-height: 1.2;
}
.box-detail {
  font-size: 0.58rem;
  color: #475569;
  line-height: 1.4;
}
.mini {
  background: rgba(0,0,0,0.05);
  border-radius: 4px;
  padding: 4px 6px;
  font-size: 0.56rem;
  line-height: 1.4;
  color: #334155;
  border: 1px solid rgba(0,0,0,0.06);
}
.mini-title {
  display: block;
  font-weight: 700;
  font-size: 0.58rem;
  margin-bottom: 1px;
}

/* ── Badges ── */
.badge {
  display: inline-block;
  padding: 1px 6px;
  border-radius: 999px;
  font-size: 0.5rem;
  font-weight: 600;
}
.badge-blue   { background: #bfdbfe; color: #1d4ed8; }
.badge-purple { background: #e9d5ff; color: #7e22ce; }
.badge-cyan   { background: #a5f3fc; color: #0e7490; }
.badge-green  { background: #bbf7d0; color: #15803d; }
.badge-orange { background: #fed7aa; color: #b45309; }
.badge-teal   { background: #a7f3d0; color: #065f46; }

/* ── Arrows ── */
.arrow-seg {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 0 6px;
  flex-shrink: 0;
  position: relative;
  min-width: 52px;
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
  font-size: 0.48rem;
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
/* vertical trunk */
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
