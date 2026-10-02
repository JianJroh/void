<template>
  <section
    class="wrapper border-t border-stroke grid md:grid-cols-2"
    aria-label="Void Platform for admins and users"
  >
    <article
      class="bg-white px-5 py-8 md:p-10 flex flex-col gap-5 border-b border-stroke md:border-r"
    >
      <div class="flex flex-col gap-5">
        <span class="text-grey text-xs font-mono uppercase tracking-wide">admin</span>
        <h3 class="text-primary text-xl md:text-3xl">Control Plane for Managing Apps</h3>
        <p class="max-w-[25rem] text-primary/70 text-base text-pretty">
          Manage users, projects, deployments, and platform health from the admin UI or CLI.
        </p>
      </div>
    </article>
    <article class="bg-white px-5 py-8 md:p-10 flex flex-col gap-5 border-b border-stroke">
      <div class="flex flex-col gap-5">
        <span class="text-grey text-xs font-mono uppercase tracking-wide">builder</span>
        <h3 class="text-primary text-xl md:text-3xl">Fast Deployment for AI Users</h3>
        <p class="max-w-[25rem] text-primary/70 text-base text-pretty">
          Connect the Void CLI to your team's platform, sign in, and deploy your app with one
          command.
        </p>
      </div>
    </article>
  </section>
</template>
