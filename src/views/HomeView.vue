<script setup>
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";
import bannerImage from "../assets/banner.webp";
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
    <article class="leading-8 max-w-3xl mx-auto text-gray-800 p-3">
      <h2 class="font-bold text-2xl mb-2 p-5">
        <span class="border-b-2 border-black inline-block max-w-[350px]">
          Välkommen till tv-serier!
        </span>
      </h2>
      <p>
        Ända sedan Game of Thrones gjorde sin premiär har serier växt till ett allt större
        intresse hos mig. I min familj har alltid filmkvällar varit veckans höjdpunkt, och
        varje helgdag hyrdes minst två filmer. Men nu har filmerna ersatts av serier.
      </p>
      <p>
        Den stora skillnaden mellan film och serie är att en serie kan utveckla karaktärer
        och berättelser på ett helt annat sätt än en film. Du blir mer fast och engagerad
        i karaktärerna, och utvecklar ett nästan familjärt band med dem.
      </p>
      <p>
        På denna sida delar jag med mig av mina favoritserier, både gamla och nya. Jag
        hoppas att du hittar något som fångar ditt intresse och ger dig lika mycket glädje
        som det ger mig!
      </p>
    </article>
  </main>

  <Footer />
</template>

<style scoped></style>
