<script setup>
import { ref } from 'vue'
import packageJson from '../package.json'

const version = ref(packageJson.version)
</script>

<template>
  <div class="version-container">
    <div class="version-card">
      <h1 class="title">当前版本</h1>
      <div class="version-number">{{ version }}</div>
      <p class="description">Version Display App</p>
    </div>
  </div>
</template>

<style scoped>
.version-container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

.version-card {
  background: rgba(255, 255, 255, 0.95);
  border-radius: 20px;
  padding: 60px 80px;
  text-align: center;
  box-shadow: 0 25px 50px rgba(0, 0, 0, 0.15);
  backdrop-filter: blur(10px);
  animation: fadeIn 0.8s ease-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.title {
  font-size: 1.8rem;
  color: #4a5568;
  margin-bottom: 20px;
  font-weight: 500;
}

.version-number {
  font-size: 8rem;
  font-weight: 700;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  line-height: 1;
  margin-bottom: 20px;
  animation: pulse 2s ease-in-out infinite;
}

@keyframes pulse {
  0%, 100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.05);
  }
}

.description {
  color: #718096;
  font-size: 1rem;
  margin: 0;
}
</style>
