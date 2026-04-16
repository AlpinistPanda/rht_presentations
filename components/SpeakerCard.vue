<script setup>
defineProps({
  name: { type: String, required: true },
  affiliation: { type: String, default: '' },
  initials: { type: String, default: '' },
})
</script>

<template>
  <div class="speaker-card">
    <div class="avatar">{{ initials || name.split(' ').map(w => w[0]).join('') }}</div>
    <div class="info">
      <div class="name">{{ name }}</div>
      <div class="affiliation">{{ affiliation }}</div>
    </div>
  </div>
</template>

<style scoped>
.speaker-card {
  display: inline-flex;
  align-items: center;
  gap: 12px;
  padding: 14px 20px 14px 14px;
  background: #f8fafc;
  border: 1px solid #e2e8f0;
  border-radius: 10px;
}

.avatar {
  width: 42px;
  height: 42px;
  border-radius: 50%;
  background: #3b82f6;
  color: white;
  font-weight: 600;
  font-size: 13px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.name {
  font-size: 14px;
  font-weight: 600;
  color: #1e293b;
  white-space: nowrap;
}

.affiliation {
  font-size: 12px;
  color: #94a3b8;
  margin-top: 3px;
  white-space: nowrap;
}
</style>
