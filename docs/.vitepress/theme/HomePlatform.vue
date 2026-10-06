<script setup>
import { Icon } from '@iconify/vue';
import { useData } from 'vitepress';

const { frontmatter } = useData();
</script>

<template>
  <div class="platform-features" data-theme="light">
    <section
      v-for="feature in frontmatter.platform_features"
      :key="feature.id"
      :aria-labelledby="feature.id"
      class="wrapper border-t border-stroke grid md:grid-cols-2 md:divide-x divide-stroke"
    >
      <div class="px-5 py-6 md:p-10 flex flex-col justify-between gap-15">
        <div class="flex flex-col gap-5">
          <Icon :icon="feature.iconify" class="size-5 text-electric" aria-hidden="true" />
          <h3 :id="feature.id" class="text-primary text-xl md:text-3xl">{{ feature.title }}</h3>
          <p class="max-w-[25rem] text-primary/70 text-base text-pretty">{{ feature.details }}</p>
          <ul class="checkmark-list">
            <li v-for="highlight in feature.highlights" :key="highlight">{{ highlight }}</li>
          </ul>
        </div>
        <a
          :href="feature.guide.link"
          class="platform-feature-link px-3 py-1.5 rounded w-fit inline-flex items-center gap-2 text-primary text-sm font-mono focus-visible:outline-2 focus-visible:outline-electric"
        >
          {{ feature.guide.text }}
          <Icon icon="lucide:arrow-up-right" class="size-4" aria-hidden="true" />
        </a>
      </div>
      <div
        class="bg-white border-t border-stroke md:border-t-0 min-h-[22rem] sm:min-h-[30rem] min-w-0 p-5 sm:p-10 flex items-center justify-center"
      >
        <img
          :src="feature.image"
          :alt="feature.image_alt"
          width="640"
          height="320"
          loading="lazy"
          class="w-full max-w-[40rem] h-auto"
        />
      </div>
    </section>
  </div>
</template>

<style scoped>
.platform-features {
  background: var(--color-white);
  color: var(--color-primary);
}

.platform-features .checkmark-list li {
  color: var(--color-primary);
}

.platform-features .checkmark-list li::before {
  filter: invert(1);
  mix-blend-mode: multiply;
}

.platform-feature-link {
  background: #f2f1f4;
}

.platform-feature-link:hover {
  background: var(--color-stroke);
}
</style>
