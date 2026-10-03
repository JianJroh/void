<script setup>
import Spacer from '@components/shared/Spacer.vue';
import { Icon } from '@iconify/vue';
</script>

<template>
  <section
    class="wrapper wrapper--ticks border-t platform-pair"
    aria-label="Void Platform management and security"
  >
    <article class="platform-panel platform-panel--control">
      <div class="platform-panel__copy">
        <h3>Control Plane for Managing Apps</h3>
        <p>Manage users, projects, deployments, and platform health from the admin UI or CLI.</p>
      </div>
      <div class="control-map" aria-hidden="true">
        <div class="control-map__group">
          <span class="control-map__node"><Icon icon="lucide:users-round" /> Users</span>
          <span class="control-map__node"><Icon icon="lucide:folder-kanban" /> Projects</span>
        </div>
        <div class="control-map__hub"><span>VOID</span><small>PLATFORM</small></div>
        <div class="control-map__group">
          <span class="control-map__node"><Icon icon="lucide:rocket" /> Deploys</span>
          <span class="control-map__node"><Icon icon="lucide:activity" /> Health</span>
        </div>
      </div>
    </article>

    <article class="platform-panel platform-panel--security">
      <div class="platform-panel__copy">
        <h3>Customize your own security</h3>
        <p>
          Choose who can access your platform and how apps are protected in your Cloudflare account.
        </p>
      </div>
      <div class="security-console" aria-hidden="true">
        <div class="security-console__bar">
          <span class="security-console__dot"></span>
          <span>Platform security</span>
          <span class="security-console__brand">VOID</span>
        </div>
        <div class="security-console__rows">
          <div>
            <Icon icon="lucide:users-round" /><span>Team access</span><Icon icon="lucide:check" />
          </div>
          <div>
            <Icon icon="lucide:key-round" /><span>Scoped credentials</span
            ><Icon icon="lucide:check" />
          </div>
          <div>
            <Icon icon="lucide:shield-check" /><span>Project protection</span
            ><Icon icon="lucide:check" />
          </div>
        </div>
      </div>
    </article>
  </section>

  <Spacer />

  <section class="wrapper border-t ai-grid" aria-label="Void for coding agents">
    <article class="ai-card ai-card--intro">
      <div class="ai-card__icon-slot">
        <span class="ai-card__featured-icon"><Icon icon="lucide:bot" aria-hidden="true" /></span>
      </div>
      <h3>Fast Deployment for AI Users</h3>
      <p>
        Give coding agents Void's project instructions, then deploy their work with the same CLI
        your team uses.
      </p>
      <a class="ai-card__link" href="/integrations/agents">
        Learn more <Icon icon="lucide:arrow-right" aria-hidden="true" />
      </a>
    </article>

    <article class="ai-card">
      <div class="ai-card__icon-slot">
        <Icon icon="lucide:book-open-check" class="ai-card__icon" aria-hidden="true" />
      </div>
      <h3>Agent-ready setup</h3>
      <p>
        <code>void init --agents</code> adds Void instructions and skills for supported coding
        agents.
      </p>
    </article>

    <article class="ai-card">
      <div class="ai-card__icon-slot">
        <Icon icon="lucide:rocket" class="ai-card__icon" aria-hidden="true" />
      </div>
      <h3>Deploy in one command</h3>
      <p>
        <code>void deploy</code> builds the app, prepares its resources, and ships it to your team's
        platform.
      </p>
    </article>
  </section>
</template>

<style scoped>
.platform-pair,
.ai-grid {
  display: grid;
}

.platform-pair {
  grid-template-columns: repeat(2, minmax(0, 1fr));
}

.platform-panel {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  min-width: 0;
  min-height: 21.5rem;
  overflow: hidden;
}

.platform-panel + .platform-panel,
.ai-card + .ai-card {
  border-left: 1px solid var(--color-stroke);
}

.platform-panel--control {
  background: #f8f8f6;
}

.platform-panel--security {
  background: #fff;
}

.platform-panel__copy {
  padding: 1.75rem 1.75rem 1.25rem;
}

.platform-panel__copy h3 {
  color: #17171b;
  font-size: clamp(1.2rem, 1.65vw, 1.5rem);
  line-height: 1.2;
  letter-spacing: -0.025em;
}

.platform-panel__copy p {
  max-width: 32ch;
  margin-top: 0.65rem;
  color: #777780;
  font-size: 0.85rem;
  line-height: 1.5;
}

.control-map {
  position: relative;
  display: grid;
  grid-template-columns: minmax(0, 1fr) auto minmax(0, 1fr);
  align-items: center;
  gap: 0.75rem;
  min-height: 12.5rem;
  padding: 0.75rem 1.5rem 1.5rem;
}

.control-map::before {
  position: absolute;
  right: 11%;
  left: 11%;
  top: 48%;
  height: 1px;
  background: #b7afff;
  content: '';
}

.control-map__group {
  z-index: 1;
  display: grid;
  justify-items: center;
  gap: 0.9rem;
  min-width: 0;
}

.control-map__node {
  display: flex;
  align-items: center;
  gap: 0.4rem;
  min-width: 5.3rem;
  padding: 0.55rem 0.65rem;
  border: 1px solid #eceaf0;
  border-radius: 0.4rem;
  background: #fff;
  box-shadow: 0 4px 12px #1813260a;
  color: #34333a;
  font-size: 0.68rem;
  white-space: nowrap;
}

.control-map__node :deep(svg) {
  width: 1rem;
  height: 1rem;
  color: #664cff;
}

.control-map__hub {
  z-index: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 5.3rem;
  height: 5.3rem;
  border: 1px solid #795fff;
  border-radius: 0.7rem;
  background: #171321;
  box-shadow: 0 10px 22px #261a571f;
  color: #fff;
  font-size: 1.25rem;
  font-weight: 800;
  letter-spacing: -0.08em;
}

.control-map__hub small {
  color: #a496ff;
  font-family: var(--font-mono);
  font-size: 0.45rem;
  font-weight: 500;
  letter-spacing: 0.08em;
}

.security-console {
  min-height: 12.5rem;
  background: #181421;
  color: #f8f7fb;
  font-family: var(--font-mono);
  font-size: 0.65rem;
}

.security-console__bar {
  display: flex;
  align-items: center;
  gap: 0.55rem;
  height: 2.5rem;
  padding: 0 1.4rem;
  border-bottom: 1px solid #ffffff19;
  color: #d8d3e4;
}

.security-console__dot {
  width: 0.45rem;
  height: 0.45rem;
  border-radius: 50%;
  background: #a080ff;
}

.security-console__brand {
  margin-left: auto;
  color: #9d96ae;
  font-weight: 700;
  letter-spacing: 0.06em;
}

.security-console__rows {
  display: grid;
  gap: 0.5rem;
  padding: 0.9rem 1.4rem;
}

.security-console__rows div {
  display: flex;
  align-items: center;
  gap: 0.65rem;
  min-height: 2.25rem;
  padding: 0 0.7rem;
  border: 1px solid #ffffff1a;
  border-radius: 0.3rem;
  background: #ffffff0a;
}

.security-console__rows :deep(svg) {
  width: 0.85rem;
  height: 0.85rem;
  color: #a48aff;
}

.security-console__rows :deep(svg:last-child) {
  margin-left: auto;
}

.ai-grid {
  grid-template-columns: minmax(0, 2fr) repeat(2, minmax(0, 1fr));
}

.ai-card {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  min-width: 0;
  min-height: 18rem;
  padding: 2rem 2.25rem;
  background: #fff;
}

.ai-card__icon-slot {
  display: flex;
  align-items: flex-start;
  height: 3.5rem;
  margin-bottom: 1.65rem;
}

.ai-card__featured-icon {
  display: grid;
  place-items: center;
  width: 3.5rem;
  height: 3rem;
  border: 1px solid #b8aaff;
  border-radius: 0.7rem;
  background: linear-gradient(145deg, #fff, #eeeaff);
  box-shadow: 0 0.35rem 0 #6548d6;
  color: #4f30e8;
  transform: rotate(-9deg);
}

.ai-card__featured-icon :deep(svg) {
  width: 1.6rem;
  height: 1.6rem;
  transform: rotate(9deg);
}

.ai-card__icon {
  width: 1.25rem;
  height: 1.25rem;
  margin-top: 0.2rem;
  color: #17171b;
}

.ai-card h3 {
  max-width: 15ch;
  color: #17171b;
  font-size: 1.1rem;
  line-height: 1.25;
  letter-spacing: -0.025em;
}

.ai-card--intro h3 {
  max-width: none;
  font-size: 1.3rem;
}

.ai-card p {
  max-width: 25ch;
  margin-top: 0.75rem;
  color: #777780;
  font-size: 0.9rem;
  line-height: 1.5;
}

.ai-card--intro p {
  max-width: 43ch;
}

.ai-card code {
  padding: 0;
  outline: 0;
  background: none;
  color: inherit;
  font-size: 0.9em;
}

.ai-card__link {
  display: inline-flex;
  align-items: center;
  gap: 0.4rem;
  margin-top: 1.25rem;
  color: #17171b;
  font-size: 0.82rem;
  text-decoration: underline;
  text-underline-offset: 2px;
}

.ai-card__link:hover {
  color: #4f30e8;
}

.ai-card__link:focus-visible {
  outline: 2px solid #4f30e8;
  outline-offset: 4px;
}

.ai-card__link :deep(svg) {
  width: 0.9rem;
  height: 0.9rem;
}

@media (max-width: 959px) {
  .ai-grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .ai-card--intro {
    grid-column: 1 / -1;
    border-bottom: 1px solid var(--color-stroke);
  }

  .ai-card:nth-child(2) {
    border-left: 0;
  }
}

@media (max-width: 767px) {
  .platform-pair {
    grid-template-columns: 1fr;
  }

  .platform-panel + .platform-panel {
    border-top: 1px solid var(--color-stroke);
    border-left: 0;
  }

  .platform-panel {
    min-height: 20rem;
  }
}

@media (max-width: 639px) {
  .ai-grid {
    grid-template-columns: 1fr;
  }

  .ai-card--intro {
    grid-column: auto;
    border-bottom: 0;
  }

  .ai-card + .ai-card {
    border-top: 1px solid var(--color-stroke);
    border-left: 0;
  }

  .ai-card {
    min-height: 0;
    padding: 2rem 1.5rem 2.5rem;
  }
}
</style>
