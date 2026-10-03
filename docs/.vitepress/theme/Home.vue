<script setup>
import Footer from '@components/oss/Footer.vue';
import Spacer from '@components/shared/Spacer.vue';
import { useData } from 'vitepress';
import bg from './hero-bg.jpg';
import Hero from './Hero.vue';
import HomeFeatures from './HomeFeatures.vue';
import HomePlatform from './HomePlatform.vue';

const { frontmatter } = useData();
</script>

<template>
  <Hero :background="bg">
    <template #hero-image>
      <div class="hero-file-tree">
        <VoidAppFileTree />
      </div>
    </template>
  </Hero>

  <Spacer />

  <section
    class="wrapper border-t border-nickel px-5 sm:px-10 h-70 sm:h-[22rem] flex flex-col justify-center gap-6 text-center items-center"
    aria-labelledby="features-heading"
  >
    <img src="/void-sdk.svg" alt="" aria-hidden="true" class="section-label" />
    <h2 id="features-heading" class="text-white">Turn Vite Apps Full-Stack</h2>
    <p class="max-w-md text-white/70 text-balance sm:text-pretty">
      Use your favorite Vite framework, add the backend features you need, and deploy with one
      command.
    </p>
  </section>

  <HomeFeatures />

  <div class="platform-surface bg-white text-primary">
    <section
      class="wrapper border-t border-stroke px-5 sm:px-10 h-70 sm:h-80 flex flex-col justify-center items-center gap-5 text-center"
      aria-labelledby="full-stack-heading"
    >
      <img src="/void-platform-dark.svg" alt="" aria-hidden="true" class="section-label" />
      <h2 id="full-stack-heading" class="text-primary text-2xl md:text-[2.5rem]">
        Deploy with your Security Built-In
      </h2>
      <p class="max-w-md text-pretty text-primary/70">
        Self-host your team's Void Platform and customize it to fit your security needs. Unlock fast
        deployment for your team.
      </p>
    </section>

    <HomePlatform />
    <Spacer />
  </div>

  <Footer
    :heading="frontmatter.footer_heading"
    :subheading="frontmatter.footer_subheading"
    button-text="Get Started"
    button-link="/guide/"
  />
</template>

<style scoped>
.hero-file-tree {
  margin-top: 2rem;
  max-width: calc(100vw - 80px);
}

.section-label {
  height: 0.9rem;
  width: auto;
}

.platform-surface :deep(.wrapper) {
  border-color: var(--color-stroke);
}

.platform-surface :deep(.wrapper--ticks::before) {
  border-left-color: var(--color-stroke);
}

.platform-surface :deep(.wrapper--ticks::after) {
  border-right-color: var(--color-stroke);
}

@media (min-width: 768px) {
  .hero-file-tree {
    margin-top: 0;
    max-width: none;
  }
}

@media (min-width: 1024px) {
  .hero-file-tree :deep(.file-tree) {
    max-height: 362px;
    overflow-y: auto;
    scrollbar-width: thin;
    scrollbar-color: rgba(255, 255, 255, 0.42) rgba(255, 255, 255, 0.08);
  }
}

.hero-file-tree :deep(.file-tree),
.hero-file-tree :deep(.adapter-tabs) {
  background-color: rgba(0, 0, 0, 0.75);
  backdrop-filter: blur(10px);
  border-color: rgba(255, 255, 255, 0.1);
}

.hero-file-tree :deep(.file-tree::-webkit-scrollbar) {
  width: 10px;
}

.hero-file-tree :deep(.file-tree::-webkit-scrollbar-track) {
  background: rgba(255, 255, 255, 0.08);
  border-radius: 999px;
}

.hero-file-tree :deep(.file-tree::-webkit-scrollbar-thumb) {
  background: rgba(255, 255, 255, 0.42);
  border: 2px solid rgba(0, 0, 0, 0.35);
  border-radius: 999px;
}

.hero-file-tree :deep(.file-tree::-webkit-scrollbar-thumb:hover) {
  background: rgba(255, 255, 255, 0.58);
}
</style>
