<template>
  <form
    @submit.prevent="addSeries"
    class="bg-white p-6 rounded-lg shadow-md max-w-md mx-auto space-y-4"
  >
    <ul v-if="errorMsg.length" class="errorMsg">
      <li class="bg-red-100 text-red-700 p-2 rounded" v-for="(msg, i) in errorMsg" :key="i">
        {{ msg }}
      </li>
    </ul>

    <!-- TITEL -->
    <div>
      <label for="title" class="block mb-1 text-sm font-medium text-gray-700">
        Titel
      </label>
      <input
        type="text"
        id="title"
        name="title"
        v-model="series"
        class="w-full p-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
      />
    </div>

    <!-- SÄSONGER -->
    <div>
      <label for="seasons" class="block mb-1 text-sm font-medium text-gray-700">
        Antal säsonger
      </label>
      <input
        type="number"
        id="seasons"
        name="seasons"
        class="w-full p-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
        v-model="seasons"
      />
    </div>

    <!-- STATUS -->
    <div>
      <label for="completed" class="block mb-1 text-sm font-medium text-gray-700">
        Pågår serien eller är den avslutad?
      </label>

      <select
        id="completed"
        name="completed"
        class="w-full p-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
        v-model="completed"
      >
        <option value="">Välj status</option>
        <option value="false">Pågående</option>
        <option value="true">Avslutad</option>
      </select>
    </div>

    <!-- SUBMIT -->
    <button
      type="submit"
      class="w-full bg-green-600 text-white font-medium py-2 px-4 rounded-lg hover:bg-blue-700 transition-colors"
    >
      Lägg till serie
    </button>
  </form>
</template>

<script setup>
import { ref } from "vue";

const series = ref("");
const seasons = ref("");
const completed = ref("");
const errorMsg = ref([]);

const emits = defineEmits(["seriesAdded"]);

const addSeries = async () => {
  errorMsg.value = [];

  if (!series.value.trim()) {
    errorMsg.value.push("Titel är obligatoriskt.");
  }

  if (!seasons.value) {
    errorMsg.value.push("Ange ett giltigt antal säsonger.");
  }

  if (!completed.value) {
    errorMsg.value.push("Välj om serien är pågående eller avslutad.");
  }

  if (errorMsg.value.length > 0) {
    return;
  }

  const data = {
    title: series.value,
    seasons: parseInt(seasons.value),
    completed: completed.value === "true",
  };

  try {
    const response = await fetch("https://tv-serier-45iu.onrender.com/series", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify(data),
    });

    if (response.ok) {
      series.value = "";
      seasons.value = "";
      completed.value = "";
      emits("seriesAdded");
    } else {
      errorMsg.value = "Fel vid tillägg av serie. Försök igen.";
    }
  } catch (error) {
    console.error("Error adding series:", error);
  }
};
</script>
