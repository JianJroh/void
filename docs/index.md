---
layout: home
theme: dark

hero:
  name: Void
  text: Full-stack apps with Vite
  tagline: Add server routes, data, and Cloudflare resources to your app. Deploy with one command.
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
    title: Choose Your Framework
    details: 'Scale your apps based on what you need: API-only, SPA + API, or full-stack.'
    highlights:
      - Native pages with React, Vue, Svelte, or Solid
      - Supports TanStack Start, React Router, SvelteKit, Nuxt, Analog, and Astro v6+
      - Rendering options including SSR, SSG, ISR, and islands
    guide:
      text: Framework integrations
      link: /integrations/frameworks/overview
  - iconify: lucide:bot
    title: Work with Coding Agents
    details: Void provides project instructions and skills to help coding agents build and deploy your app.
    highlights:
      - Project instructions from void init --agents
      - Version-matched documentation
      - Skills for building and migrating Void apps
    guide:
      text: Coding agents guide
      link: /integrations/agents

footer_heading: Build with Vite. Deploy with Void.
footer_subheading: Server code, resources, and deployment in one workflow.
---

<script setup>
import Home from './.vitepress/theme/Home.vue'
</script>

<Home />
