<template>
  <section class="editorial-flood-opening">
    <div class="opening-copy">
      <p class="eyebrow">Urban flood resilience</p>
      <h1>Flooding is a global planning problem.</h1>
      <p class="dek">
        The most common natural disaster worldwide is also one of the hardest
        risks for cities to plan around.
      </p>
    </div>

    <div class="visual-grid" aria-label="Editorial flood risk visual">
      <figure class="flood-image-slot">
        <!-- Replace this placeholder with a licensed/sourced flood photograph.
             Suggested crop: wide urban street flooding, darkened for contrast. -->
        <div class="photo-placeholder">
          <span>Flood image placeholder</span>
          <strong>Insert final sourced image</strong>
        </div>
      </figure>

      <figure class="editorial-chart">
        <figcaption>
          <span>Worldwide natural disaster occurrence</span>
          <strong>Floods rank first</strong>
        </figcaption>

        <!-- Data note: insert verified source and counts before final publication.
             The chart intentionally avoids fabricated numbers. -->
        <svg viewBox="0 0 640 410" role="img" aria-labelledby="floodChartTitle floodChartDesc">
          <title id="floodChartTitle">Floods are the most common natural disaster worldwide</title>
          <desc id="floodChartDesc">
            Editorial ranking graphic showing floods as the leading natural disaster category.
          </desc>

          <defs>
            <linearGradient id="floodBar" x1="0" x2="1">
              <stop offset="0%" stop-color="#38bdf8" />
              <stop offset="100%" stop-color="#0ea5e9" />
            </linearGradient>
            <pattern id="editorialHatch" width="8" height="8" patternUnits="userSpaceOnUse" patternTransform="rotate(45)">
              <line x1="0" y1="0" x2="0" y2="8" stroke="#334155" stroke-width="3" />
            </pattern>
          </defs>

          <line x1="124" y1="64" x2="590" y2="64" class="rule" />
          <line x1="124" y1="148" x2="590" y2="148" class="rule" />
          <line x1="124" y1="232" x2="590" y2="232" class="rule" />
          <line x1="124" y1="316" x2="590" y2="316" class="rule" />

          <text x="40" y="70" class="rank">01</text>
          <text x="92" y="70" class="label flood-label">Floods</text>
          <rect x="190" y="42" width="378" height="44" rx="4" fill="url(#floodBar)" />
          <text x="582" y="70" class="bar-note">most common</text>

          <text x="40" y="154" class="rank muted">02</text>
          <text x="92" y="154" class="label">Other hazards</text>
          <rect x="190" y="126" width="250" height="44" rx="4" class="secondary-bar" />

          <text x="40" y="238" class="rank muted">03</text>
          <text x="92" y="238" class="label">Other hazards</text>
          <rect x="190" y="210" width="204" height="44" rx="4" class="secondary-bar" />

          <text x="40" y="322" class="rank muted">04</text>
          <text x="92" y="322" class="label">Other hazards</text>
          <rect x="190" y="294" width="160" height="44" rx="4" class="secondary-bar hatch" />

          <text x="40" y="384" class="source-note">
            Replace placeholders with verified disaster category counts and source.
          </text>
        </svg>
      </figure>
    </div>
  </section>
</template>

<style scoped>
.editorial-flood-opening {
  position: relative;
  display: grid;
  grid-template-columns: minmax(0, 0.92fr) minmax(0, 1.38fr);
  gap: 42px;
  height: 100%;
  min-height: 520px;
  padding: 34px 50px 44px;
  color: #f8fafc;
  background:
    radial-gradient(circle at 82% 16%, rgba(56, 189, 248, 0.14), transparent 34%),
    linear-gradient(135deg, #020617 0%, #0f172a 58%, #111827 100%);
  overflow: hidden;
}

.editorial-flood-opening::before {
  content: "";
  position: absolute;
  inset: 22px;
  border: 1px solid rgba(226, 232, 240, 0.08);
  pointer-events: none;
}

.opening-copy {
  position: relative;
  z-index: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  max-width: 455px;
}

.eyebrow {
  margin: 0 0 22px;
  color: #38bdf8;
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 0.16em;
  text-transform: uppercase;
}

h1 {
  margin: 0;
  font-size: 3.25rem;
  line-height: 0.96;
  letter-spacing: 0;
  font-weight: 760;
}

.dek {
  max-width: 390px;
  margin: 28px 0 0;
  color: #cbd5e1;
  font-size: 1.02rem;
  line-height: 1.5;
}

.visual-grid {
  position: relative;
  z-index: 1;
  display: grid;
  grid-template-rows: 0.82fr 1.18fr;
  gap: 18px;
  min-width: 0;
}

figure {
  margin: 0;
}

.flood-image-slot {
  position: relative;
  overflow: hidden;
  border-radius: 8px;
  background:
    linear-gradient(180deg, rgba(2, 6, 23, 0.08), rgba(2, 6, 23, 0.82)),
    linear-gradient(115deg, rgba(15, 23, 42, 0.92), rgba(14, 165, 233, 0.32)),
    url("/img/screen.png");
  background-size: cover;
  background-position: center;
  min-height: 176px;
  box-shadow: 0 22px 58px rgba(0, 0, 0, 0.34);
}

.flood-image-slot::after {
  content: "";
  position: absolute;
  inset: 0;
  background:
    linear-gradient(90deg, transparent 0 44%, rgba(56, 189, 248, 0.22) 44% 45%, transparent 45%),
    repeating-linear-gradient(0deg, rgba(255, 255, 255, 0.05) 0 1px, transparent 1px 18px);
  mix-blend-mode: screen;
  opacity: 0.58;
}

.photo-placeholder {
  position: absolute;
  left: 22px;
  bottom: 20px;
  z-index: 1;
  display: flex;
  flex-direction: column;
  gap: 3px;
  color: #e2e8f0;
  text-shadow: 0 2px 18px rgba(0, 0, 0, 0.7);
}

.photo-placeholder span {
  font-size: 0.72rem;
  text-transform: uppercase;
  letter-spacing: 0.14em;
  color: #bae6fd;
}

.photo-placeholder strong {
  font-size: 1.2rem;
  font-weight: 700;
}

.editorial-chart {
  overflow: hidden;
  border-radius: 8px;
  border: 1px solid rgba(148, 163, 184, 0.24);
  background: #f8fafc;
  color: #0f172a;
  box-shadow: 0 22px 58px rgba(0, 0, 0, 0.34);
}

figcaption {
  display: flex;
  align-items: end;
  justify-content: space-between;
  gap: 20px;
  padding: 18px 22px 8px;
  border-bottom: 1px solid #cbd5e1;
  font-family: Georgia, "Times New Roman", serif;
}

figcaption span {
  max-width: 250px;
  color: #475569;
  font-size: 0.84rem;
  line-height: 1.25;
}

figcaption strong {
  color: #020617;
  font-size: 1.52rem;
  line-height: 1;
  font-weight: 700;
}

svg {
  display: block;
  width: 100%;
  height: 286px;
}

.rule {
  stroke: #cbd5e1;
  stroke-width: 1;
}

.rank {
  fill: #0f172a;
  font-size: 18px;
  font-weight: 800;
  font-variant-numeric: tabular-nums;
}

.rank.muted,
.label {
  fill: #64748b;
}

.label {
  font-size: 18px;
  font-weight: 650;
}

.flood-label {
  fill: #0284c7;
}

.secondary-bar {
  fill: #dbe4ec;
}

.hatch {
  fill: url(#editorialHatch);
}

.bar-note {
  fill: #075985;
  font-size: 15px;
  font-weight: 750;
  text-anchor: end;
}

.source-note {
  fill: #64748b;
  font-size: 13px;
}

@media (max-width: 900px) {
  .editorial-flood-opening {
    grid-template-columns: 1fr;
    gap: 24px;
    padding: 28px 34px 38px;
  }

  .opening-copy {
    max-width: none;
    justify-content: start;
  }

  h1 {
    font-size: 2.42rem;
  }

  .visual-grid {
    grid-template-rows: 150px minmax(250px, 1fr);
  }
}
</style>
