<script setup>
import { RouterView, RouterLink } from 'vue-router'
</script>

<template>

    <header class="bg-white shadow p-4">
      <h1 class="text-3xl font-bold text-center mb-3">TV Serier</h1>

      <nav>
        <ul class="flex justify-center gap-6 text-lg">
          <li>
            <RouterLink
              to="/"
              class="hover:text-blue-600 transition-colors font-medium"
            >Startsida</RouterLink>
          </li>
          <li>
            <RouterLink
              to="/list"
              class="hover:text-blue-600 transition-colors font-medium"
            >Tv-serier</RouterLink>
          </li>
          <li>
            <RouterLink
              to="/info"
              class="hover:text-blue-600 transition-colors font-medium"
            >Info</RouterLink>
          </li>
        </ul>
      </nav>
    </header>
      <RouterView />

</template>
