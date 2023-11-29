<template>
    <section>
        <h3>{{ experience?.name }}</h3>
        <img :src="`/images/${experience?.image}`" :alt="`${experience?.name}`" class="large-image" />
        <p>{{ experience?.description }}</p>
    </section>
</template>

<script setup lang="ts">
import { computed } from "vue";
import data from "@/data.json";
const props = defineProps<{
    id: number;
    experienceSlug: string;
}>();

const destination = computed(() => {
    return data.destinations.find((destination) => destination.id === props.id);
});

const experience = computed(() => {
    return destination.value?.experiences.find(
        (experience) => experience.slug === props.experienceSlug
    );
});
</script>

<style scoped>
.large-image {
    width: 500px;
    max-width: 800px;
    height: auto;
}
</style>