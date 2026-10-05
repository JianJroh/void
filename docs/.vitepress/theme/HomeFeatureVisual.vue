<script setup lang="ts">
import RiveAnimation from '@components/shared/RiveAnimation.vue';
import frameworksAnimation from './assets/animations/640_x_320_vite_frameworks_diamond.riv';
import connectorsAnimation from './assets/animations/640_x_320_void_connectors.riv';

defineProps<{
  kind: 'deploy' | 'stack' | 'frameworks';
}>();

const descriptions = {
  deploy: 'Illustrative terminal showing the steps in a Void deployment.',
  stack: 'Animated illustration of Void connectors.',
  frameworks: 'Animated illustration of Void framework integrations.',
};
</script>

<template>
  <div
    class="feature-visual"
    :class="`feature-visual--${kind}`"
    role="img"
    :aria-label="descriptions[kind]"
  >
    <div v-if="kind === 'deploy'" class="terminal">
      <div class="terminal-bar">
        <div class="terminal-dots"><span></span><span></span><span></span></div>
        <span>Void CLI · example</span>
      </div>
      <div class="terminal-body">
        <p><span class="prompt">$</span> void deploy</p>
        <p class="muted">Building your app...</p>
        <p><span class="success">✓</span> Build complete</p>
        <p><span class="success">✓</span> Resources ready</p>
        <p><span class="success">✓</span> Migrations checked</p>
        <p><span class="success">✓</span> Deployed to Cloudflare Workers</p>
      </div>
    </div>

    <div v-else-if="kind === 'stack'" class="feature-animation">
      <RiveAnimation
        :desktop-src="connectorsAnimation"
        :desktop-width="640"
        :desktop-height="320"
        canvas-class="w-full h-auto"
      />
    </div>

    <div v-else-if="kind === 'frameworks'" class="feature-animation">
      <RiveAnimation
        :desktop-src="frameworksAnimation"
        :desktop-width="640"
        :desktop-height="320"
        state-machines="State Machine 1"
        canvas-class="w-full h-auto"
      />
    </div>
  </div>
</template>

<style scoped>
.feature-visual {
  display: grid;
  place-items: center;
  width: 100%;
  height: 17rem;
  overflow: hidden;
  border: 1px solid rgba(255, 255, 255, 0.12);
  border-radius: 8px;
}

.feature-visual--deploy {
  padding: 1rem;
  background: #211763 url('./hero-bg.jpg') center / cover;
}

.terminal {
  width: min(100%, 29rem);
  overflow: hidden;
  border: 1px solid rgba(255, 255, 255, 0.22);
  border-radius: 8px;
  background: rgba(16, 14, 23, 0.94);
  box-shadow: 0 16px 38px rgba(8, 5, 20, 0.38);
  color: #f4f1ff;
  font-family: var(--font-mono);
  font-size: 0.72rem;
}

.terminal-bar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0.55rem 0.8rem;
  border-bottom: 1px solid rgba(255, 255, 255, 0.12);
  color: #a9a2b9;
  font-size: 0.65rem;
}

.terminal-dots {
  display: flex;
  gap: 0.3rem;
}

.terminal-dots span {
  width: 0.4rem;
  height: 0.4rem;
  border-radius: 50%;
  background: #6d657e;
}

.terminal-body {
  display: grid;
  gap: 0.32rem;
  padding: 0.8rem;
}

.terminal-body p {
  margin: 0;
  color: #e9e5f2;
  font-size: inherit;
  line-height: 1.35;
}

.terminal-body .prompt {
  color: #b39aff;
}

.terminal-body .muted {
  color: #aaa4b6;
}

.terminal-body .success {
  color: #22ff73;
}

.feature-visual--stack,
.feature-visual--frameworks {
  border: 0;
  background: transparent;
}

.feature-animation {
  width: 100%;
  max-width: 40rem;
}

@media (min-width: 768px) {
  .feature-visual {
    height: 20rem;
  }
}
</style>
