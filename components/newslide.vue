<template>
  <div class="simulation-wrapper" @click="handleNextStep">
    <!-- Top Instruction -->
    <div class="instruction">
      {{ instructions[step] }}
    </div>

    <div class="diagram-container">
      <!-- 1. Models Box (Appears Step 2) -->
      <transition name="fade">
        <div v-if="step >= 2" class="box model-box">
          <img 
            src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?auto=format&fit=crop&q=80&w=400" 
            alt="Delft3D Model"
          />
          <span class="label">Delft3D Flood Model</span>
        </div>
      </transition>

      <!-- Arrow 1 (Appears Step 2) -->
      <transition name="fade">
        <div v-if="step >= 2" class="arrow-group">
          <span class="arrow-text">Simulation</span>
          <span class="arrow-icon">➔</span>
        </div>
      </transition>

      <!-- 2. Data Box (Appears Step 2) -->
      <transition name="fade">
        <div v-if="step >= 2" class="box data-box">
          <div class="data-icon">📊</div>
          <div class="data-stats">
            Water Depth: 2.4m<br>
            Velocity: 1.2m/s
          </div>
          <span class="label">Simulation Results</span>
        </div>
      </transition>

      <!-- Arrow 2 (The Broken/Faded one) -->
      <transition name="fade">
        <div 
          v-if="step >= 2" 
          class="arrow-group" 
          :class="{ 'broken': step === 2, 'fixed': step === 3 }"
        >
          <span class="arrow-text">{{ step === 3 ? 'Shared Knowledge' : 'Communication Gap' }}</span>
          <span class="arrow-icon">{{ step === 3 ? '➔' : '⇢' }}</span>
        </div>
      </transition>

      <!-- 3. Decision Maker Box (Appears Step 1) -->
      <transition name="fade">
        <div 
          v-if="step >= 1" 
          class="box dm-box" 
          :class="{ 'participatory': step === 3 }"
        >
          <div class="people-icons">
            <span v-if="step < 3">👤</span>
            <span v-else>👥👤👥</span>
          </div>
          <span class="label">
            {{ step === 3 ? 'Participatory Decision Making' : 'Decision Maker' }}
          </span>
          <div v-if="step === 3" class="badge">Inclusive</div>
        </div>
      </transition>
    </div>

    <button class="reset-btn" @click.stop="step = 0">Reset</button>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const step = ref(0);

const instructions = [
  "Click anywhere to begin...",
  "The Decision Maker is waiting for information. Click to run the models.",
  "Results are ready, but there's a gap in communication. Click to bridge it.",
  "Success: Community-led modeling bridges the gap!"
];

const handleNextStep = () => {
  if (step.value < 3) {
    step.value++;
  }
};
</script>

<style scoped>
.simulation-wrapper {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-color: #f8fafc;
  font-family: sans-serif;
  cursor: pointer;
  user-select: none;
  position: relative;
}

.instruction {
  position: absolute;
  top: 40px;
  font-size: 1.2rem;
  color: #64748b;
  font-style: italic;
  text-align: center;
}

.diagram-container {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 20px;
  width: 95%;
  max-width: 1100px;
}

/* Box Styling */
.box {
  background: white;
  border: 2px solid #cbd5e1;
  border-radius: 16px;
  padding: 24px;
  width: 220px;
  text-align: center;
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
}

.box img {
  width: 100%;
  height: 100px;
  object-fit: cover;
  border-radius: 8px;
  margin-bottom: 12px;
}

.label {
  display: block;
  font-weight: 700;
  color: #1e293b;
  font-size: 0.9rem;
  margin-top: 8px;
}

/* Specific Box Variants */
.data-icon {
  font-size: 3rem;
}
.data-stats {
  font-size: 0.75rem;
  color: #64748b;
  margin: 8px 0;
  font-family: monospace;
}

.people-icons {
  font-size: 3rem;
  margin-bottom: 8px;
  transition: all 0.3s ease;
}

.participatory {
  border-color: #3b82f6;
  background-color: #eff6ff;
  transform: scale(1.05);
  box-shadow: 0 20px 25px -5px rgba(59, 130, 246, 0.2);
}

.badge {
  display: inline-block;
  background: #3b82f6;
  color: white;
  font-size: 0.7rem;
  padding: 2px 8px;
  border-radius: 99px;
  margin-top: 8px;
  animation: pulse 2s infinite;
}

/* Arrows */
.arrow-group {
  display: flex;
  flex-direction: column;
  align-items: center;
  min-width: 80px;
  transition: all 0.5s ease;
}

.arrow-text {
  font-size: 0.7rem;
  font-weight: 600;
  color: #94a3b8;
  margin-bottom: 4px;
  text-transform: uppercase;
}

.arrow-icon {
  font-size: 2rem;
  color: #3b82f6;
}

.broken {
  opacity: 0.3;
}
.broken .arrow-icon {
  color: #94a3b8;
}

.fixed .arrow-icon {
  color: #3b82f6;
  animation: slideIn 0.5s ease-out;
}
.fixed .arrow-text {
  color: #3b82f6;
}

/* Reset Button */
.reset-btn {
  position: absolute;
  bottom: 40px;
  padding: 8px 16px;
  background: #e2e8f0;
  border: none;
  border-radius: 6px;
  color: #475569;
  cursor: pointer;
}
.reset-btn:hover { background: #cbd5e1; }

/* Transitions & Animations */
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.8s ease, transform 0.8s ease;
}
.fade-enter-from {
  opacity: 0;
  transform: translateY(20px);
}

@keyframes pulse {
  0% { transform: scale(1); }
  50% { transform: scale(1.05); }
  100% { transform: scale(1); }
}

@keyframes slideIn {
  from { transform: translateX(-10px); opacity: 0; }
  to { transform: translateX(0); opacity: 1; }
}
</style>