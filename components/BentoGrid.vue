<script setup>
/**
 * BentoGrid — reusable Tailwind bento-layout card for Slidev.
 *
 * Usage in slides.md:
 *
 *   <BentoGrid
 *     eyebrow="Deploy faster"
 *     title="Everything you need to deploy your app"
 *     :items="[...]"
 *   />
 *
 * Each item in :items follows the BentoItem shape (see defaults below).
 */

const props = withDefaults(defineProps({
  /** Small coloured label above the main title */
  eyebrow: {
    type: String,
    default: 'Deploy faster',
  },
  /** Main heading */
  title: {
    type: String,
    default: 'Everything you need to deploy your app',
  },
  /** Accent colour for the eyebrow text (any valid CSS colour) */
  accentColor: {
    type: String,
    default: '#4f46e5',
  },
  /**
   * Array of bento items. Four items are expected for the 3-column layout.
   * Shape:
   *   {
   *     title:       string
   *     description: string
   *     image:       string   (URL or path)
   *     imageAlt?:   string
   *     type:        'phone' | 'graph' | 'security' | 'code'
   *     // 'phone'    → left tall card   (row-span-2, phone frame mockup)
   *     // 'graph'    → top-middle card
   *     // 'security' → bottom-middle card
   *     // 'code'     → right tall card  (row-span-2, dark editor mockup)
   *   }
   */
  items: {
    type: Array,
    default: () => [
      {
        title: 'Mobile friendly',
        description: 'Anim aute id magna aliqua ad ad non deserunt sunt. Qui irure qui lorem cupidatat commodo.',
        image: 'https://tailwindcss.com/plus-assets/img/component-images/bento-03-mobile-friendly.png',
        imageAlt: 'Mobile friendly screenshot',
        type: 'phone',
      },
      {
        title: 'Performance',
        description: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit maiores impedit.',
        image: 'https://tailwindcss.com/plus-assets/img/component-images/bento-03-performance.png',
        imageAlt: 'Performance chart',
        type: 'graph',
      },
      {
        title: 'Security',
        description: 'Morbi viverra dui mi arcu sed. Tellus semper adipiscing suspendisse semper morbi.',
        image: 'https://tailwindcss.com/plus-assets/img/component-images/bento-03-security.png',
        imageAlt: 'Security icons',
        type: 'security',
      },
      {
        title: 'Powerful APIs',
        description: 'Sit quis amet rutrum tellus ullamcorper ultricies libero dolor eget sem sodales gravida.',
        image: '',
        imageAlt: '',
        type: 'code',
        /** Optional: file tabs shown in the editor header */
        codeTabs: ['NotificationSetting.jsx', 'App.jsx'],
      },
    ],
  },
}), {})

/** Helpers */
const phone    = computed(() => props.items.find(i => i.type === 'phone'))
const graph    = computed(() => props.items.find(i => i.type === 'graph'))
const security = computed(() => props.items.find(i => i.type === 'security'))
const code     = computed(() => props.items.find(i => i.type === 'code'))

import { computed } from 'vue'
</script>

<template>
  <div class="bg-gray-50 py-10 sm:py-12">
    <div class="mx-auto max-w-2xl px-6 lg:max-w-7xl lg:px-8">

      <!-- ── Header ── -->
      <h2
        class="text-center text-sm font-semibold tracking-wide uppercase"
        :style="{ color: accentColor }"
      >
        {{ eyebrow }}
      </h2>
      <p class="mx-auto mt-2 max-w-lg text-center text-3xl font-semibold tracking-tight text-gray-950 sm:text-4xl">
        {{ title }}
      </p>

      <!-- ── Grid ── -->
      <div class="mt-8 grid gap-4 sm:mt-10 lg:grid-cols-3 lg:grid-rows-2">

        <!-- ── CELL 1: Phone (left, tall) ── -->
        <div v-if="phone" class="relative lg:row-span-2">
          <div class="absolute inset-px rounded-lg bg-white lg:rounded-l-[2rem]" />
          <div class="relative flex h-full flex-col overflow-hidden rounded-[calc(0.5rem+1px)] lg:rounded-l-[calc(2rem+1px)]">
            <div class="px-8 pt-8 pb-3 sm:px-10 sm:pt-10 sm:pb-0">
              <p class="mt-2 text-base font-semibold tracking-tight text-gray-950 max-lg:text-center">
                {{ phone.title }}
              </p>
              <p class="mt-2 max-w-lg text-sm leading-6 text-gray-600 max-lg:text-center">
                {{ phone.description }}
              </p>
            </div>
            <!-- Phone frame -->
            <div class="relative min-h-[280px] w-full grow max-lg:mx-auto max-lg:max-w-sm">
              <div class="absolute inset-x-10 top-10 bottom-0 overflow-hidden rounded-t-[2rem] border-x-[3px] border-t-[3px] border-gray-700 bg-gray-900 shadow-2xl">
                <img
                  v-if="phone.image"
                  :src="phone.image"
                  :alt="phone.imageAlt || phone.title"
                  class="size-full object-cover object-top"
                />
              </div>
            </div>
          </div>
          <div class="pointer-events-none absolute inset-px rounded-lg shadow-sm ring-1 ring-black/5 lg:rounded-l-[2rem]" />
        </div>

        <!-- ── CELL 2: Graph (top-middle) ── -->
        <div v-if="graph" class="relative max-lg:row-start-1">
          <div class="absolute inset-px rounded-lg bg-white max-lg:rounded-t-[2rem]" />
          <div class="relative flex h-full flex-col overflow-hidden rounded-[calc(0.5rem+1px)] max-lg:rounded-t-[calc(2rem+1px)]">
            <div class="px-8 pt-8 sm:px-10 sm:pt-10">
              <p class="mt-2 text-base font-semibold tracking-tight text-gray-950 max-lg:text-center">
                {{ graph.title }}
              </p>
              <p class="mt-2 max-w-lg text-sm leading-6 text-gray-600 max-lg:text-center">
                {{ graph.description }}
              </p>
            </div>
            <div class="flex flex-1 items-center justify-center px-8 max-lg:pt-8 max-lg:pb-10 sm:px-10 lg:pb-2">
              <img
                v-if="graph.image"
                :src="graph.image"
                :alt="graph.imageAlt || graph.title"
                class="w-full max-lg:max-w-xs"
              />
            </div>
          </div>
          <div class="pointer-events-none absolute inset-px rounded-lg shadow-sm ring-1 ring-black/5 max-lg:rounded-t-[2rem]" />
        </div>

        <!-- ── CELL 3: Security (bottom-middle) ── -->
        <div v-if="security" class="relative max-lg:row-start-3 lg:col-start-2 lg:row-start-2">
          <div class="absolute inset-px rounded-lg bg-white" />
          <div class="relative flex h-full flex-col overflow-hidden rounded-[calc(0.5rem+1px)]">
            <div class="px-8 pt-8 sm:px-10 sm:pt-10">
              <p class="mt-2 text-base font-semibold tracking-tight text-gray-950 max-lg:text-center">
                {{ security.title }}
              </p>
              <p class="mt-2 max-w-lg text-sm leading-6 text-gray-600 max-lg:text-center">
                {{ security.description }}
              </p>
            </div>
            <div class="flex flex-1 items-center max-lg:py-6 lg:pb-2">
              <img
                v-if="security.image"
                :src="security.image"
                :alt="security.imageAlt || security.title"
                class="h-[152px] object-cover"
              />
            </div>
          </div>
          <div class="pointer-events-none absolute inset-px rounded-lg shadow-sm ring-1 ring-black/5" />
        </div>

        <!-- ── CELL 4: Code editor (right, tall) ── -->
        <div v-if="code" class="relative lg:row-span-2">
          <div class="absolute inset-px rounded-lg bg-white max-lg:rounded-b-[2rem] lg:rounded-r-[2rem]" />
          <div class="relative flex h-full flex-col overflow-hidden rounded-[calc(0.5rem+1px)] max-lg:rounded-b-[calc(2rem+1px)] lg:rounded-r-[calc(2rem+1px)]">
            <div class="px-8 pt-8 pb-3 sm:px-10 sm:pt-10 sm:pb-0">
              <p class="mt-2 text-base font-semibold tracking-tight text-gray-950 max-lg:text-center">
                {{ code.title }}
              </p>
              <p class="mt-2 max-w-lg text-sm leading-6 text-gray-600 max-lg:text-center">
                {{ code.description }}
              </p>
            </div>
            <!-- Dark editor mockup -->
            <div class="relative min-h-[280px] w-full grow">
              <div class="absolute top-8 right-0 bottom-0 left-8 overflow-hidden rounded-tl-xl bg-gray-900 shadow-2xl ring-1 ring-white/10">
                <!-- Tab bar -->
                <div class="flex bg-gray-800/60 ring-1 ring-white/5">
                  <div class="-mb-px flex text-xs font-medium text-gray-400">
                    <template v-if="code.codeTabs && code.codeTabs.length">
                      <div
                        v-for="(tab, ti) in code.codeTabs"
                        :key="tab"
                        :class="[
                          'px-4 py-2 border-r',
                          ti === 0
                            ? 'border-r-white/10 border-b border-b-white/20 bg-white/5 text-white'
                            : 'border-gray-600/10 text-gray-400'
                        ]"
                      >
                        {{ tab }}
                      </div>
                    </template>
                  </div>
                </div>
                <!-- Code area / slot -->
                <div class="px-6 pt-6 pb-14 text-xs text-gray-300 leading-5">
                  <slot name="code">
                    <!-- Default placeholder code -->
                    <span class="text-purple-400">import</span>
                    <span class="text-gray-300"> &#123; ref &#125; </span>
                    <span class="text-purple-400">from</span>
                    <span class="text-yellow-300"> 'vue'</span><br/><br/>
                    <span class="text-purple-400">const</span>
                    <span class="text-blue-300"> enabled </span>
                    <span class="text-gray-300">= ref(</span>
                    <span class="text-orange-300">true</span>
                    <span class="text-gray-300">)</span><br/><br/>
                    <span class="text-green-400">// Toggle notification setting</span><br/>
                    <span class="text-purple-400">function</span>
                    <span class="text-yellow-200"> toggle</span>
                    <span class="text-gray-300">() &#123;</span><br/>
                    <span class="text-gray-300">  enabled.value = !enabled.value</span><br/>
                    <span class="text-gray-300">&#125;</span>
                  </slot>
                </div>
              </div>
            </div>
          </div>
          <div class="pointer-events-none absolute inset-px rounded-lg shadow-sm ring-1 ring-black/5 max-lg:rounded-b-[2rem] lg:rounded-r-[2rem]" />
        </div>

      </div>
    </div>
  </div>
</template>
