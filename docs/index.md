---
layout: home
theme: dark

hero:
  name: Void
  text: Launch Vite Apps at Warp Speed
  tagline: Void is a full-stack SDK, platform and CLI that unifies building & deploying apps
  actions:
    - theme: brand
      text: Get Started
      link: ./guide/
    - theme: alt
      text: View on Github
      link: https://github.com/voidzero-dev/void
features:
  - iconify: lucide:layers
    visual: stack
    title: Full-Stack Features
    details: Use a database, KV, object storage, AI, authentication, queues, and cron jobs as your app needs them.
    highlights:
      - Server routes and pages
      - Database, KV, and object storage
      - AI, queues, and scheduled jobs
    guide:
      text: Explore app types
      link: /guide/app-types
  - iconify: lucide:wand-sparkles
    visual: resources
    title: Resources from Your Code
    details: Void detects supported resources from your imports and provisions them on deploy. Configure existing resources explicitly.
    highlights:
      - Database, KV, and storage inferred from imports
      - Local resources for development
      - Types shared between server loaders and pages
    guide:
      text: Resource inference guide
      link: /reference/resource-inference
  - iconify: lucide:blocks
    visual: frameworks
    title: Choose Your Framework
    details: 'Scale your apps based on what you need: API-only, SPA + API, or full-stack.'
    highlights:
      - Native pages with React, Vue, Svelte, or Solid
      - Supports TanStack Start, React Router, SvelteKit, Nuxt, Analog, and Astro v6+
      - Rendering options including SSR, SSG, ISR, and islands
    guide:
      text: Framework integrations
      link: /integrations/frameworks/overview
footer_heading: Build with Vite. Deploy with Void.
footer_subheading: Server code, resources, and deployment in one workflow.
---

<script setup>
import Home from './.vitepress/theme/Home.vue'
</script>

<Home />
