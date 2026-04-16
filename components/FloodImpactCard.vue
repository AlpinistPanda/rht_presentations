<template>
  <div class="wrap">
    <div class="card">

      <div class="headline-row">
        <span class="headline-text">Urban flood losses — global economic impact</span>
      </div>

      <div class="stat-grid">
        <div class="stat-cell">
          <p class="stat-label">Annual losses</p>
          <p class="stat-number" style="color: #993C1D;">$82B</p>
          <p class="stat-desc">Current global urban flood damages per year</p>
        </div>
        <div class="stat-cell">
          <p class="stat-label">By 2050</p>
          <p class="stat-number" style="color: #D85A30;">$1T+</p>
          <p class="stat-desc">Projected annual losses under moderate warming</p>
        </div>
        <div class="stat-cell">
          <p class="stat-label">Exposure growth</p>
          <p class="stat-number">2.1×</p>
          <p class="stat-desc">Increase in people living in flood-prone urban areas since 1990</p>
        </div>
      </div>

      <div class="trend-section">
        <p class="trend-label">Major urban flood events per decade</p>
        <div v-for="row in bars" :key="row.year" class="bar-row">
          <span class="bar-year">{{ row.year }}</span>
          <div class="bar-track">
            <div class="bar-fill" :style="{ width: row.pct }"></div>
          </div>
          <span class="bar-val">{{ row.val }}</span>
        </div>
      </div>

      <p class="source-line">Sources: Swiss Re Institute · World Resources Institute · IPCC AR6 · Munich Re NatCatSERVICE</p>
    </div>
  </div>
</template>

<script setup>
const bars = [
  { year: '1980s', pct: '18%',  val: '~42'     },
  { year: '1990s', pct: '30%',  val: '~71'     },
  { year: '2000s', pct: '55%',  val: '~128'    },
  { year: '2010s', pct: '78%',  val: '~184'    },
  { year: '2020s', pct: '100%', val: '↑ accel.' },
]
</script>

<style scoped>
.wrap {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #ffffff;
  padding: 3rem 4rem;
  box-sizing: border-box;
}

.card {
  width: 100%;
  max-width: 860px;
  padding: 2rem 2.5rem;
  background: #ffffff;
  border: 0.5px solid #e5e7eb;
  border-radius: 16px;
  box-shadow: 0 1px 4px rgba(0,0,0,0.06);
}

.headline-row {
  display: flex;
  align-items: baseline;
  padding: 0 0 1.25rem;
  border-bottom: 0.5px solid #e5e7eb;
  margin-bottom: 1.5rem;
}
.headline-text {
  font-size: 16px;
  font-weight: 500;
  color: #374151;
}

.stat-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1px;
  background: #e5e7eb;
  border: 0.5px solid #e5e7eb;
  border-radius: 12px;
  overflow: hidden;
  margin-bottom: 2rem;
}
.stat-cell {
  background: #ffffff;
  padding: 1.5rem 1.25rem;
}
.stat-label {
  font-size: 11px;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  color: #9ca3af;
  margin: 0 0 8px;
}
.stat-number {
  font-size: 36px;
  font-weight: 500;
  color: #111827;
  margin: 0 0 6px;
  line-height: 1;
}
.stat-desc {
  font-size: 13px;
  color: #6b7280;
  margin: 0;
  line-height: 1.5;
}

.trend-section {
  margin-top: 1.75rem;
}
.trend-label {
  font-size: 11px;
  text-transform: uppercase;
  letter-spacing: 0.07em;
  color: #9ca3af;
  margin: 0 0 12px;
}
.bar-row {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 10px;
}
.bar-year {
  font-size: 13px;
  color: #6b7280;
  width: 40px;
  flex-shrink: 0;
}
.bar-track {
  flex: 1;
  height: 7px;
  background: #f3f4f6;
  border-radius: 4px;
  overflow: hidden;
}
.bar-fill {
  height: 100%;
  border-radius: 4px;
  background: #D85A30;
}
.bar-val {
  font-size: 13px;
  color: #6b7280;
  width: 60px;
  text-align: right;
  flex-shrink: 0;
}

.source-line {
  font-size: 11px;
  color: #9ca3af;
  margin-top: 1.5rem;
  padding-top: 1rem;
  border-top: 0.5px solid #e5e7eb;
}
</style>
