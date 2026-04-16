<template>
  <div class="w-full px-6 py-2 flex flex-col gap-4 font-sans">

    <!-- ── Step 0 & 1: primary diagram ── -->
    <div
      class="grid items-center gap-0 transition-opacity duration-500"
      style="grid-template-columns: 220px 100px 1fr;"
      :class="step >= 2 ? 'opacity-20' : 'opacity-100'"
    >

      <!-- Left column: Model (top) + Data (bottom) -->
      <div class="flex flex-col gap-4">

        <!-- Model box -->
        <div
          class="flex flex-col gap-2 bg-white border border-gray-200 rounded-lg shadow-sm p-4 transition-all duration-500"
          :class="step >= 1 ? 'opacity-100 translate-x-0' : 'opacity-0 -translate-x-3'"
        >
          <div class="w-full h-20 bg-gray-100 rounded flex items-center justify-center overflow-hidden">
            <img
              src="/img/model.png"
              alt="Hydrological model"
              class="w-full h-full object-cover"
              @error="(e) => e.target.style.display = 'none'"
            />
            <span class="text-gray-400 text-xs uppercase tracking-widest absolute">Model image</span>
          </div>
          <div>
            <p class="text-gray-900 text-sm font-semibold leading-tight">Hydrological Model</p>
            <p class="text-gray-400 text-xs uppercase tracking-wider mt-0.5">Delft3D · SFINCS · HEC-RAS</p>
          </div>
        </div>

        <!-- Data box -->
        <div
          class="flex flex-col gap-2 bg-white border border-gray-200 rounded-lg shadow-sm p-4 transition-all duration-500 delay-150"
          :class="step >= 1 ? 'opacity-100 translate-x-0' : 'opacity-0 -translate-x-3'"
        >
          <div class="w-full h-20 bg-gray-100 rounded flex items-center justify-center overflow-hidden">
            <img
              src="/img/data.jpg"
              alt="Urban data"
              class="w-full h-full object-cover"
              @error="(e) => e.target.style.display = 'none'"
            />
            <span class="text-gray-400 text-xs uppercase tracking-widest absolute">Data image</span>
          </div>
          <div>
            <p class="text-gray-900 text-sm font-semibold leading-tight">Urban Data</p>
            <p class="text-gray-400 text-xs uppercase tracking-wider mt-0.5">GIS · Sensors · Census</p>
          </div>
        </div>

      </div>

      <!-- Arrow column -->
      <div
        class="relative flex flex-col h-full items-center justify-center transition-opacity duration-500 delay-300"
        :class="step >= 1 ? 'opacity-100' : 'opacity-0'"
      >
        <!-- Top arrow: Model → DM -->
        <svg class="w-full" style="height:80px;" viewBox="0 0 80 80" preserveAspectRatio="none" fill="none">
          <line x1="4" y1="74" x2="72" y2="6"
                stroke="#94a3b8" stroke-width="1.5" stroke-dasharray="5 5"/>
          <polygon points="72,6 60,14 66,20" fill="#94a3b8" opacity="0.5"/>
        </svg>

        <!-- "no link" badge -->
        <div
          class="absolute bg-red-50 border border-red-200 text-red-500 text-center px-2 py-1 rounded transition-opacity duration-500 delay-700"
          :class="step >= 1 ? 'opacity-100' : 'opacity-0'"
          style="font-size:0.48rem; letter-spacing:0.1em; text-transform:uppercase; line-height:1.4;"
        >
          no direct<br/>channel
        </div>

        <!-- Bottom arrow: Data → DM -->
        <svg class="w-full" style="height:80px;" viewBox="0 0 80 80" preserveAspectRatio="none" fill="none">
          <line x1="4" y1="6" x2="72" y2="74"
                stroke="#94a3b8" stroke-width="1.5" stroke-dasharray="5 5"/>
          <polygon points="72,74 60,60 66,68" fill="#94a3b8" opacity="0.5"/>
        </svg>
      </div>

      <!-- Right: Decision Maker -->
      <div class="flex items-center justify-start pl-4">
        <div class="flex flex-col gap-2 bg-white border border-gray-900 rounded-lg shadow-md p-4 w-full">
          <div class="w-full h-24 bg-gray-100 rounded flex items-center justify-center overflow-hidden relative">
            <img
              src="/img/decision-maker.jpg"
              alt="Decision maker"
              class=" object-cover"
              @error="(e) => e.target.style.display = 'none'"
            />
          </div>
          <div>
            <p class="text-gray-900 text-sm font-semibold leading-tight">Decision Maker</p>
            <p class="text-gray-400 text-xs uppercase tracking-wider mt-0.5">City Planner</p>
          </div>
        </div>
      </div>

    </div>

    <!-- ── Step 2: siloed stacks ── -->
    <div
      class="flex flex-col gap-3 transition-all duration-500"
      :class="step >= 2 ? 'opacity-100 translate-y-0' : 'opacity-0 translate-y-3'"
    >
      <p class="text-xs uppercase tracking-widest text-gray-400 border-t border-gray-200 pt-3">
        Each actor operates in isolation
      </p>

      <div class="grid grid-cols-3 gap-4">
        <div
          v-for="(silo, i) in silos"
          :key="i"
          class="bg-white border border-gray-200 rounded-lg shadow-sm p-3 flex flex-col gap-2 transition-all duration-400"
          :class="step >= 2 ? 'opacity-100 translate-y-0' : 'opacity-0 translate-y-2'"
          :style="{ transitionDelay: step >= 2 ? (i * 120) + 'ms' : '0ms' }"
        >
          <!-- Silo header: actor label -->
          <p class="text-gray-900 text-xs font-semibold uppercase tracking-wide border-b border-gray-100 pb-1">
            {{ silo.label }}
          </p>

          <!-- Mini model + data + person row -->
          <div class="flex items-center gap-2">

            <!-- Mini model + data stacked -->
            <div class="flex flex-col gap-1.5 flex-1">
              <div class="flex items-center gap-1.5 bg-gray-50 border border-gray-200 rounded px-2 py-1">
                <div class="w-8 h-6 bg-gray-200 rounded overflow-hidden flex-shrink-0 relative">
                  <img
                    src="/img/model.png"
                    class="w-full h-full object-cover"
                    @error="(e) => e.target.style.display = 'none'"
                  />
                </div>
                <span class="text-gray-500 text-[9px] uppercase tracking-wider">Model</span>
              </div>
              <div class="flex items-center gap-1.5 bg-gray-50 border border-gray-200 rounded px-2 py-1">
                <div class="w-8 h-6 bg-gray-200 rounded overflow-hidden flex-shrink-0 relative">
                  <img
                    src="/img/data.jpg"
                    class="w-full h-full object-cover"
                    @error="(e) => e.target.style.display = 'none'"
                  />
                </div>
                <span class="text-gray-500 text-[9px] uppercase tracking-wider">Data</span>
              </div>
            </div>

            <!-- Broken arrows -->
            <svg width="24" height="44" viewBox="0 0 24 44" fill="none" flex-shrink-0>
              <line x1="2" y1="38" x2="22" y2="6" stroke="#d1d5db" stroke-width="1.2" stroke-dasharray="3 3"/>
              <line x1="2" y1="6" x2="22" y2="38" stroke="#d1d5db" stroke-width="1.2" stroke-dasharray="3 3"/>
            </svg>

            <!-- Mini person -->
            <div class="flex flex-col items-center gap-1 flex-shrink-0">
              <div class="w-10 h-10 bg-gray-100 border border-gray-200 rounded overflow-hidden relative">
                <img
                  src="/img/decision-maker.jpg"
                  class="w-full h-full object-cover"
                  @error="(e) => e.target.style.display = 'none'"
                />
              </div>
              <span class="text-gray-400 text-[8px] text-center leading-tight">{{ silo.actor }}</span>
            </div>

          </div>
        </div>
      </div>
    </div>

  </div>
</template>

<script setup>
defineProps({
  step: { type: Number, default: 0 },
})

const silos = [
  { label: 'Municipality',    actor: 'City Planner' },
  { label: 'Water Board',     actor: 'Engineer' },
  { label: 'NGO / Community', actor: 'Representative' },
]
</script>
