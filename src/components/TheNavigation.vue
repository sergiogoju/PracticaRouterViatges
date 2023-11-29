<template>
  <div class="nav-bar">
    <ul>
      <router-link :to="'/'">
        <h2>Home</h2>
      </router-link>
      <router-link v-for="destination in data" :key="destination.id" :to="{
        name: 'destination.show',
        params: { id: destination.id, slug: destination.slug },
      }" tag="li">
        <h2>{{ destination.name }}</h2>
      </router-link>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import dades from "@/data.json";

const data = ref(dades.destinations);
</script>

<style scoped>
.nav-bar {
  background-color: #1a237e;
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1000;
}

ul {
  list-style-type: none;
  margin: 0;
  display: flex;
}

h2 {
  color: #fff;
  padding-right: 3rem;
}

h2:hover {
  color: #00f7ff;
}
</style>
