<template>
  <div class="home">
    <h1>All Destinations</h1>
    <div class="destinations">
      <router-link v-for="destination in destinations" :key="destination.id" :to="{
        name: 'destination.show',
        params: { id: destination.id, slug: destination.slug },
      }">
        <h2>{{ destination.name }}</h2>
        <img :src="`/images/${destination.image}`" :alt="destination.name" />
      </router-link>
      <router-view></router-view>
    </div>
  </div>
</template>

<script setup lang="ts">
import data from "@/data.json";
import { ref } from "vue";

const destinations = ref(data.destinations);

</script>


