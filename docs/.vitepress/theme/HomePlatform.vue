<script setup>
import placeholderImage from './feature-placeholder.svg';
</script>

<template>
  <section
    class="wrapper border-t border-stroke grid sm:grid-cols-2 divide-y sm:divide-y-0 sm:divide-x divide-stroke"
    aria-label="Void Platform for admins and users"
  >
    <div class="bg-white p-5 sm:p-10 flex flex-col justify-between gap-10">
      <div class="flex flex-col gap-3">
        <span class="text-grey text-xs font-mono uppercase tracking-wide">admin</span>
        <h3 class="text-primary text-xl sm:text-2xl">Control Plane for Admins</h3>
        <p class="max-w-[20rem] text-primary/70 text-balance">
          Manage users, projects, deployments, and platform health from the admin UI or CLI.
        </p>
      </div>
      <img :src="placeholderImage" alt="" class="w-full" loading="lazy" />
    </div>
    <div class="bg-white p-5 sm:p-10 flex flex-col justify-between gap-10">
      <div class="flex flex-col gap-3">
        <span class="text-grey text-xs font-mono uppercase tracking-wide">user</span>
        <h3 class="text-primary text-xl sm:text-2xl">Deployment for Vibe-coders</h3>
        <p class="max-w-[20rem] text-primary/70 text-balance">
          Connect the Void CLI to your team's platform, sign in, and deploy your app with one
          command.
        </p>
      </div>
      <img :src="placeholderImage" alt="" class="w-full" loading="lazy" />
    </div>
  </section>
</template>
