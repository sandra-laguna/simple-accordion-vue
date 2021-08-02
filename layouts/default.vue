<template>
  <div class="relative w-full h-full pt-20">
    <app-navbar />

    <app-main>
      <transition mode="out-in">
        <nuxt :key="$route.fullPath" />
      </transition>
    </app-main>

    <app-footer />
  </div>
</template>
