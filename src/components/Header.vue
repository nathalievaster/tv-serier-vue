<script setup>
import { RouterView, RouterLink } from 'vue-router'
</script>

<template>
    <RouterView />
  <header>
    <h1>TV Serier</h1>
  <nav>
    <ul>
      <li><RouterLink to="/">Home</RouterLink></li>
      <li><RouterLink to="/list">List</RouterLink></li>
      <li><RouterLink to="/info">Info</RouterLink></li>
    </ul>
  </nav>
    </header>
</template>
