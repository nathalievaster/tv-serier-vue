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
        console.log("data från API:", data);

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
    <article class="home">
      <h2>Lägg till tv-serier i listan</h2>
      <p>Lägg till eller ta bort tv-serier ur listan nedan.</p>
    </article>
    <SeriesItem v-for="serie in series" :serie="serie" :key="serie._id"/>
  </main>
  <Footer />
</template>

<style scoped></style>
