---
layout: home
theme: dark

hero:
  name: Void
  text: Ship Vite Apps at Warp Speed
  tagline: Void is an SDK, platform and CLI that unifies build and deploy so apps go from local save to global production.
  actions:
    - theme: brand
      text: Get Started
      link: ./guide/
    - theme: alt
      text: View on Github
      link: https://github.com/voidzero-dev/void
  image:
    src: /hero.svg
    alt: Void deployment platform

features:
  - iconify: lucide:terminal
    visual: deploy
    title: Deploy with One Command
    command: void deploy
    details: builds your app, provisions resources, applies migrations, and deploys it.
    highlights:
      - Deploy to Cloudflare Workers or a Void platform
      - Provision D1, KV, and R2 as your app uses them
      - Validate and apply database migrations
    guide:
      text: Deployment guide
      link: /guide/deployment
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
