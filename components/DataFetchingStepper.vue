<template>
    <div class="stepper-container">
      <div class="stepper">
        <div class="stepper-line"></div>
        <div 
          v-for="(step, index) in steps" 
          :key="index"
          class="step"
          :class="{ 
            'active': currentStep === index,
            'server': index === 0,
            'client': index === steps.length - 1
          }"
          :style="{ left: `${(index / (steps.length - 1)) * 100}%` }"
        >
          <div class="step-dot"></div>
          <div class="step-label" :class="{ 'active': currentStep === index }">
            {{ step.label }}
          </div>
        </div>
      </div>
      <div class="spectrum-labels">
        <span class="server-label">Server</span>
        <span class="client-label">Client</span>
      </div>
    </div>
  </template>
  
  <script setup>
  const props = defineProps({
    currentStep: {
      type: Number,
      default: 0
    }
  })
  
  const steps = [
    { label: 'Critical Data' },
    { label: 'Prefetched Data' },
    { label: 'Dynamic Streaming' },
    { label: 'Client-only' }
  ]
  </script>
  
  <style scoped>
  .stepper-container {
    padding: 0.5rem;
    margin: 0.5rem 0;
    height: 50px;
  }
  
  .stepper {
    position: relative;
    height: 40px;
    width: 100%;
  }
  
  .stepper-line {
    position: absolute;
    top: 8px;
    width: 100%;
    height: 2px;
    background: linear-gradient(to right, var(--slidev-theme-accents-teal), var(--slidev-theme-accents-red));
  }
  
  .step {
    position: absolute;
    transform: translateX(-50%);
    text-align: center;
  }
  
  .step-dot {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background: var(--slidev-theme-background);
    border: 2px solid var(--slidev-theme-accents-purple);
    margin: 4px auto;
    transition: all 0.3s ease;
  }
  
  .step.active .step-dot {
    width: 14px;
    height: 14px;
    margin: 2px auto;
    background: var(--slidev-theme-accents-purple);
    box-shadow: 0 0 0 3px rgba(179, 157, 219, 0.2);
  }
  
  .step-label {
    font-size: 0.7rem;
    color: var(--slidev-theme-color);
    opacity: 0.7;
    transition: all 0.3s ease;
    white-space: nowrap;
  }
  
  .step-label.active {
    font-weight: bold;
    opacity: 1;
    color: var(--slidev-theme-accents-purple);
  }
  
  .spectrum-labels {
    display: flex;
    justify-content: space-between;
    margin-top: 0.25rem;
    font-size: 0.7rem;
  }
  
  .server-label {
    color: var(--slidev-theme-accents-teal);
    font-weight: bold;
  }
  
  .client-label {
    color: var(--slidev-theme-accents-red);
    font-weight: bold;
  }
  
  .step.server .step-dot {
    border-color: var(--slidev-theme-accents-teal);
  }
  
  .step.server.active .step-dot {
    background: var(--slidev-theme-accents-teal);
  }
  
  .step.client .step-dot {
    border-color: var(--slidev-theme-accents-red);
  }
  
  .step.client.active .step-dot {
    background: var(--slidev-theme-accents-red);
  }
  </style>