<script setup>
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";
import bannerImage from '../assets/banner.webp'
</script>

<template>
  <Header />

  <!-- Banner -->
<section class="relative w-full h-64 md:h-96 mb-6">
  <img :src="bannerImage" alt="Bannerbild" class="w-full h-full object-cover block" />
  <!--- Overlay -->
    <div class="absolute inset-0 bg-black bg-opacity-50 flex items-center justify-center">
      <h2 class="text-white text-3xl md:text-5xl font-bold">TV-serier</h2>
    </div>
  </section>

  <main class="p-6 max-w-4xl mx-auto">
    <article class="home">
      <h2 class="font-bold text-2xl mb-2">Välkommen till tv-serier!</h2>
      <p>Här kan du skriva kort information om ditt fritidsintresse.</p>
    </article>
  </main>

  <Footer />
</template>


<style scoped></style>
