<template>
    <div class="card">
        <img v-if="experience" :src="`/images/${experience.image}`" :alt="experience.name" />
        <span v-if="experience" class="card__text">
            {{ experience.name }}
        </span>
        <span v-else>Error: Experience not found</span>
    </div>
</template>
  
<script setup lang="ts">
import { defineProps } from 'vue';

const props = defineProps(['experience']);
</script>
  