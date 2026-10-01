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
    <h2 id="features-heading" class="text-white">Full-Stack Apps with Vite</h2>
    <p class="max-w-md text-white/70 text-balance sm:text-pretty">
      Use your favorite Vite framework, add the backend features you need, and deploy with one
      command.
    </p>
  </section>

  <HomeFeatures />

  <div class="bg-white text-primary">
    <section
      class="wrapper border-t border-stroke px-5 sm:px-10 h-70 sm:h-80 flex flex-col justify-center gap-5"
      aria-labelledby="full-stack-heading"
    >
      <h2 id="full-stack-heading" class="text-primary text-2xl md:text-[2.5rem]">
        Self-host Void Platform
      </h2>
      <p class="max-w-md text-pretty text-primary/70">
        Run Void Platform in your team's Cloudflare account. Manage projects centrally while
        developers deploy from the CLI.
      </p>
    </section>

    <HomePlatform />
  </div>

  <Spacer />

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
