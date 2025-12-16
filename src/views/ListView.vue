<script setup>
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";
import SeriesItem from "../components/SeriesItem.vue";
import { ref, onMounted } from "vue";

const series = ref([])

onMounted (() => {
  getSeries();
})

const getSeries = async () => {
  try {
    const response = await fetch("https://tv-serier-45iu.onrender.com/series");

    if (response.ok) {
      const data = await response.json();

      series.value = data;
    }
  } catch (error) {
    console.error("Error fetching series:", error);
  }
};
</script>

<template>
  <Header />

  <main class="p-6 max-w-4xl mx-auto">
    <section class="mb-6">
      <h2 class="text-3xl font-bold mb-2 border-b-2 border-gray-300 w-max">
        Tv-serier
      </h2>
      <p class="text-gray-600 mt-2">
        Lägg till eller ta bort tv-serier ur listan nedan.
      </p>
    </section>

    <section>
      <SeriesItem
        v-for="serie in series"
        :key="serie._id"
        :serie="serie"
      />
    </section>
  </main>

  <Footer />
</template>
<style scoped></style>
