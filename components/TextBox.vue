<template>
  <div
    class="text-box"
    :class="[
      fullWidth ? 'w-full' : 'w-fit',
      noBorder ? '' : 'border border-black/10',
    ]"
  >
    <div v-if="label" class="text-box-label">{{ label }}</div>
    <div class="text-box-body">
      <slot />
    </div>
  </div>
</template>

<script setup>
defineProps({
  /** Optional uppercase label shown above the content */
  label: { type: String, default: '' },
  /** Stretch to full container width */
  fullWidth: { type: Boolean, default: false },
  /** Remove the border */
  noBorder: { type: Boolean, default: false },
})
</script>

<style scoped>
.text-box {
  background: #ffffff;
  color: #0a0a0a;
  padding: 1rem 1.25rem;
  font-family: 'Inter', 'Helvetica Neue', sans-serif;
  line-height: 1.6;
  position: relative;
}

.text-box-label {
  font-size: 0.55rem;
  font-weight: 700;
  letter-spacing: 0.14em;
  text-transform: uppercase;
  color: #6b7280;
  margin-bottom: 0.5rem;
  padding-bottom: 0.4rem;
  border-bottom: 1px solid #e5e7eb;
}

.text-box-body {
  font-size: 0.9rem;
  color: #0a0a0a;
}

/* Pass-through: Tailwind classes on the slot content still work */
.text-box-body :deep(p) { margin: 0 0 0.5rem; }
.text-box-body :deep(p:last-child) { margin-bottom: 0; }
.text-box-body :deep(strong) { font-weight: 700; color: #000; }
.text-box-body :deep(em) { color: #374151; font-style: italic; }
</style>
