<template>
  <header>
    <TheNavigation></TheNavigation>
  </header>
  <div class="container">
    <router-view v-slot="{ Component }">
      <component :is="Component" :key="$route.path" />
    </router-view>
  </div>
</template>

<script setup lang="ts">
import TheNavigation from '@/components/TheNavigation.vue';
</script>

<style></style>
