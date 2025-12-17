<script setup>
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";
</script>

<template>
  <Header />
  <main class="p-6 max-w-4xl mx-auto">
    <article class="leading-8 max-w-3xl mx-auto text-gray-800 p-3">
      <h2>Om uppgiften</h2>
      <div class="p-6">
      <p>Det har varit mycket lätt och roligt att arbeta med Vue! Det påminner lite om
      Angular som jag tyckte var något av det roligaste vi jobbat med. Ska bli kul att 
      jobba vidare med Vue, och utvärdera vilket jag tycker är bäst.</p>
      <p>Malins filmer har varit till stor hjälp - mycket pedagogiskt och lätt att komma 
      in i tänket och kunna bygga vidare.</p>
      <p>Jag ville testa använda tailwind för att kombinera ramverk. Det är såhär Tailwind 
      är tänkt att användas, i komponenter. Jag är fortfarande tveksamt inställd till Tailwind
      och om det verkligen förenklar arbetet. Tycker snarare tvärtom, och kommer nog i 
      projektet använda vanlig CSS istället. Det fina med Vue är ju att CSS skrivs i komponenterna
      och de olika uppdelade filerna, vilket gör det enkelt att hålla koden strukturerad och lätt att underhålla.
      Då känns inte Tailwind lika nödvändigt.</p>
      </div>
    </article>
  </main>
  <Footer />
</template>

<style scoped></style>
