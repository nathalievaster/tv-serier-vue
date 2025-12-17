<template>
  <form @submit.prevent="addSeries">
    <p class="errorMsg" v-if="errorMsg">{{ errorMsg }}</p>
    <label for="title">Titel:</label>
    <input type="text" id="title" name="title" v-model="series" />
    <label for="seasons">Antal säsonger:</label>
    <input type="number" id="seasons" name="seasons" />
    <label for="completed" class="block mb-2 text-sm font-medium text-gray-700">
      Pågår serien eller är den avslutad?
    </label>

    <select
      id="completed"
      name="completed"
      class="w-full p-2 border border-gray-300 rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-500"
    >
      <option value="">Välj status</option>
      <option value="false">Pågående</option>
      <option value="true">Avslutad</option>
    </select>
    <button type="submit">Lägg till serie</button>
  </form>
</template>

<script setup>
import { ref } from "vue";

const series = ref("");
const errorMsg = ref("");

const emits = defineEmits(["seriesAdded"]);

const addSeries = async () => {
    if (!series.value.trim()) {
        errorMsg.value = "Titel är obligatoriskt.";
        return;
    }
    if (!seasons.value) {
        errorMsg.value = "Ange ett giltigt antal säsonger.";
        return;
    }
    if (!completed.value) {
        errorMsg.value = "Välj om serien är pågående eller avslutad.";
        return;
    }
    errorMsg.value = "";

    const data = {
        title: series.value,
        seasons: parseInt(seasons.value),
        completed: completed.value === "true",
    }

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
}
</script>
