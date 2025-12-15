<script setup>
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";
import SeriesItem from "../components/SeriesItem.vue";
import { ref } from "vue";

const series = ref([
 {
  serie: "Stranger Things",
  _id: 1
 },
  {
    serie: "The Crown",
    _id: 2
  },
  {
    serie: "Breaking Bad",
    _id: 3
  },
  {
    serie: "The Mandalorian",
    _id: 4
  }
]);
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
