<template>
  <div class="w-full h-full bg-gray-50 flex flex-col justify-center px-6 py-4 font-sans select-none">

    <!-- ── Bento grid: 3 cols × 3 rows ── -->
    <div class="grid grid-cols-3 grid-rows-3 gap-3 flex-1 min-h-0">

      <!-- ① FAIR4RS — col-span-2, row-span-1, with image placeholder -->
      <div class="bento-card col-span-2 row-span-1 flex gap-4 items-stretch" style="background:#f0f9ff; border-color:#38bdf8;">
        <div class="flex flex-col justify-center flex-1">
          <div class="flex items-center gap-2 mb-1">
            <span class="icon-chip" style="background:#e0f2fe; color:#0369a1;">✦</span>
            <span class="card-title text-sky-800">FAIR4RS Principles</span>
          </div>
          <p class="card-desc">Follows <strong>FAIR for Research Software</strong> guidelines — Findable, Accessible, Interoperable, Reusable. Metadata, licensing and persistent identifiers aligned with open science standards.</p>
          <div class="flex gap-1.5 mt-2 flex-wrap">
            <span class="chip" style="background:#bae6fd;color:#075985;">Findable</span>
            <span class="chip" style="background:#bae6fd;color:#075985;">Accessible</span>
            <span class="chip" style="background:#bae6fd;color:#075985;">Interoperable</span>
            <span class="chip" style="background:#bae6fd;color:#075985;">Reusable</span>
          </div>
        </div>
        <!-- Image placeholder -->
        <div class="img-placeholder" style="min-width:110px; border-color:#7dd3fc;">
          <img v-if="false" src="/img/github.png" alt="" class="w-full h-full object-cover rounded-lg"/>
          <div class="placeholder-inner">
            <span class="placeholder-icon">📄</span>
            <span class="placeholder-label">FAIR4RS paper</span>
          </div>
        </div>
      </div>

      <!-- ② Version Controlled — col-span-1, row-span-2, tall, with image -->
      <div class="bento-card col-span-1 row-span-2 flex flex-col" style="background:#0f172a; border-color:#334155;">
        <div class="flex items-center gap-2 mb-1.5">
          <span class="icon-chip" style="background:#1e293b; color:#94a3b8;">⎇</span>
          <span class="card-title" style="color:#f1f5f9;">Version Controlled</span>
        </div>
        <p class="card-desc" style="color:#94a3b8;">Full git history on GitHub. Branching strategy, tagged releases, and contributor workflows following open-source conventions.</p>
        <div class="flex gap-1.5 mt-1.5 flex-wrap">
          <span class="chip" style="background:#1e293b;color:#7dd3fc;">Git</span>
          <span class="chip" style="background:#1e293b;color:#7dd3fc;">GitHub</span>
          <span class="chip" style="background:#1e293b;color:#7dd3fc;">Releases</span>
        </div>
        <!-- Image placeholder -->
        <div class="img-placeholder flex-1 mt-2" style="border-color:#334155; background:#1e293b;">
          <img src="/img/github.png" alt="GitHub" class="w-full h-full object-cover rounded-lg"/>
        </div>
      </div>

      <!-- ③ Dockerized — col-span-1, row-span-1 -->
      <div class="bento-card col-span-1 row-span-1" style="background:#eff6ff; border-color:#60a5fa;">
        <div class="flex items-center gap-2 mb-1">
          <span class="icon-chip" style="background:#dbeafe; color:#1d4ed8;">⬡</span>
          <span class="card-title text-blue-800">Fully Dockerized</span>
        </div>
        <p class="card-desc">Entire stack runs in Docker Compose — NGINX, Django, SvelteKit, TiTiler, PostgreSQL. One command deploy on SURF Research Cloud.</p>
        <div class="flex gap-1.5 mt-auto pt-2 flex-wrap">
          <span class="chip" style="background:#bfdbfe;color:#1e40af;">Docker Compose</span>
          <span class="chip" style="background:#bfdbfe;color:#1e40af;">SURF Cloud</span>
        </div>
      </div>

      <!-- ④ Open Source — col-span-1, row-span-1 -->
      <div class="bento-card col-span-1 row-span-1" style="background:#f0fdf4; border-color:#4ade80;">
        <div class="flex items-center gap-2 mb-1">
          <span class="icon-chip" style="background:#dcfce7; color:#15803d;">◎</span>
          <span class="card-title text-green-800">Open Source</span>
        </div>
        <p class="card-desc">Published under an open license. Codebase, ontology, and documentation are publicly accessible and reusable by the research community.</p>
        <div class="flex gap-1.5 mt-auto pt-2 flex-wrap">
          <span class="chip" style="background:#bbf7d0;color:#166534;">MIT / Apache</span>
          <span class="chip" style="background:#bbf7d0;color:#166534;">Public repo</span>
        </div>
      </div>

      <!-- ⑤ CI/CD — col-span-1, row-span-1 -->
      <div class="bento-card col-span-1 row-span-1" style="background:#fdf4ff; border-color:#c084fc;">
        <div class="flex items-center gap-2 mb-1">
          <span class="icon-chip" style="background:#f3e8ff; color:#7e22ce;">↻</span>
          <span class="card-title text-purple-800">CI / CD</span>
        </div>
        <p class="card-desc">GitHub Actions pipelines for automated linting, testing, and deployment. Every push to main triggers a build and deploy to GitHub Pages.</p>
        <div class="flex gap-1.5 mt-auto pt-2 flex-wrap">
          <span class="chip" style="background:#e9d5ff;color:#6b21a8;">GH Actions</span>
          <span class="chip" style="background:#e9d5ff;color:#6b21a8;">Auto-deploy</span>
        </div>
      </div>

      <!-- ⑥ Testing — col-span-2, row-span-1 -->
      <div class="bento-card col-span-2 row-span-1 flex gap-4 items-stretch" style="background:#fff7ed; border-color:#fb923c;">
        <div class="flex flex-col justify-center flex-1">
          <div class="flex items-center gap-2 mb-1">
            <span class="icon-chip" style="background:#ffedd5; color:#c2410c;">✓</span>
            <span class="card-title text-orange-800">Testing</span>
          </div>
          <p class="card-desc">Backend covered by Django unit and integration tests. API endpoints validated against real database instances. Frontend component tests with Vitest.</p>
          <div class="flex gap-1.5 mt-2 flex-wrap">
            <span class="chip" style="background:#fed7aa;color:#9a3412;">Django TestCase</span>
            <span class="chip" style="background:#fed7aa;color:#9a3412;">Pytest</span>
            <span class="chip" style="background:#fed7aa;color:#9a3412;">Vitest</span>
            <span class="chip" style="background:#fed7aa;color:#9a3412;">Integration DB</span>
          </div>
        </div>
        <!-- Coverage placeholder -->
        <div class="img-placeholder" style="min-width:100px; border-color:#fdba74;">
          <img v-if="false" src="" alt="" class="w-full h-full object-cover rounded-lg"/>
          <div class="placeholder-inner">
            <span class="placeholder-icon">🧪</span>
            <span class="placeholder-label">Coverage report</span>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>

<script setup>
</script>

<style scoped>
.bento-card {
  border-radius: 14px;
  border-width: 1px;
  border-style: solid;
  padding: 12px 14px;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  box-shadow: 0 1px 3px rgba(0,0,0,0.06);
}

.icon-chip {
  width: 22px;
  height: 22px;
  border-radius: 6px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.65rem;
  flex-shrink: 0;
}

.card-title {
  font-size: 0.72rem;
  font-weight: 700;
  line-height: 1.2;
}

.card-desc {
  font-size: 0.55rem;
  color: #475569;
  line-height: 1.5;
}

.chip {
  display: inline-block;
  padding: 1px 7px;
  border-radius: 999px;
  font-size: 0.46rem;
  font-weight: 600;
}

/* ── Image placeholder ── */
.img-placeholder {
  border: 1.5px dashed;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  background: rgba(255,255,255,0.5);
}

.placeholder-inner {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 4px;
  pointer-events: none;
}

.placeholder-icon {
  font-size: 1.4rem;
  opacity: 0.5;
}

.placeholder-label {
  font-size: 0.44rem;
  color: #94a3b8;
  font-weight: 500;
  letter-spacing: 0.04em;
  text-align: center;
}
</style>
