<template>
  <article
    class="bg-white rounded-lg shadow-sm p-4 mb-4 hover:shadow-md transition-shadow flex justify-between items-center"
  >
    <!-- VÄNSTER: INFO -->
    <div>
      <h3 class="text-xl font-semibold text-gray-800">
        {{ serie.title }}
      </h3>

      <p v-if="serie.seasons" class="text-gray-600 text-sm mt-1">
        Säsonger: {{ serie.seasons }}
      </p>

      <span
        class="inline-block mt-2 text-sm font-medium px-3 py-1 rounded-full"
        :class="
          serie.completed
            ? 'bg-green-100 text-green-700'
            : 'bg-yellow-100 text-yellow-700'
        "
      >
        {{ serie.completed ? "Avslutad" : "Pågående" }}
      </span>
    </div>

    <!-- HÖGER: DELETE-KNAPP -->
    <button @click ="$emit('deleteSerie', serie.id)"
      class="ml-4 px-4 py-2 text-sm font-medium text-red-600 border border-red-200 rounded-lg 
      hover:bg-red-50 hover:border-red-300 transition-colors"type="button">Ta bort</button>
  </article>
</template>

<script setup>
const props = defineProps({
  serie: Object,
});

const emit = defineEmits(["deleteSerie"]);
</script>

<style scoped></style>
