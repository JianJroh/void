<script setup lang="ts">
import RiveAnimation from '@components/shared/RiveAnimation.vue';
import frameworksAnimation from './assets/animations/639_x_320_flexible_plugin_cloudflare_void.riv';
import voidLogo from './void-dark.svg';

defineProps<{
  kind: 'deploy' | 'stack' | 'frameworks';
}>();

const capabilities = [
  'Serverless edge',
  'Database',
  'Key-value cache',
  'Object storage',
  'Queues',
  'Cron jobs',
  'API layer',
  'Email',
  'AI inference',
];

const descriptions = {
  deploy: 'Illustrative terminal showing the steps in a Void deployment.',
  stack: 'Void brings edge runtime, data, storage, jobs, email, and AI together.',
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

    <div v-else-if="kind === 'stack'" class="stack-diagram">
      <ul class="stack-list">
        <li v-for="capability in capabilities" :key="capability">{{ capability }}</li>
      </ul>
      <svg class="stack-brace" viewBox="0 0 60 240" preserveAspectRatio="none" focusable="false">
        <path
          d="M2 2H18C43 2 43 17 43 40V94C43 111 48 118 58 120C48 122 43 129 43 146V200C43 223 43 238 18 238H2"
        />
      </svg>
      <img :src="voidLogo" alt="" class="stack-logo" />
    </div>

    <div v-else-if="kind === 'frameworks'" class="framework-animation">
      <RiveAnimation
        :desktop-src="frameworksAnimation"
        :desktop-width="639"
        :desktop-height="320"
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

.feature-visual--stack {
  border-color: #e2e1e8;
  background: #fbfbfd;
}

.stack-diagram {
  display: grid;
  grid-template-columns: minmax(0, 1.5fr) 2.6rem minmax(0, 1fr);
  align-items: center;
  gap: 0.5rem;
  width: 100%;
  height: 100%;
  padding: 1rem;
}

.stack-list {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;
  margin: 0;
  padding: 0;
  list-style: none;
}

.stack-list li {
  color: #16171d;
  font-family: var(--font-heading);
  font-size: clamp(0.65rem, 1.1vw, 0.86rem);
  font-weight: 500;
  line-height: 1.15;
  white-space: nowrap;
}

.stack-brace {
  width: 100%;
  height: 100%;
  fill: none;
  stroke: #16171d;
  stroke-linecap: round;
  stroke-linejoin: round;
  stroke-width: 3;
}

.stack-logo {
  width: 100%;
  max-width: 10rem;
  height: auto;
}

.feature-visual--frameworks {
  border: 0;
  background: transparent;
}

.framework-animation {
  width: 100%;
  max-width: 40rem;
}

@media (min-width: 768px) {
  .feature-visual {
    height: 20rem;
  }
}
</style>
