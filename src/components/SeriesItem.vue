<template>
    <article> {{ serie.title }} </article>
</template>

<script setup>
    const props = defineProps({
        serie: Object
    });
</script>

<style scoped>
    p {
        background-color: black;
        padding: 10px;
        color: white;
    }
</style>