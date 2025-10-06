<script setup lang="ts"></script>

<template>
  <div class="container">
    <a class="home" href="/"><h1 class="name">Karo Moret</h1></a>
    <div class="links">
      <a href="/about">About</a>
      <a href="/media">Media</a>
      <a href="/contact">Contact</a>
    </div>
  </div>
</template>

<style scoped lang="scss">
.container {
  padding: 1rem;
  background-image: url('/images/nav.webp');
  background-repeat: no-repeat;
  background-size: cover;

  .home {
    text-decoration: none;
    color: black;

    .name {
      margin: 0 0 1rem 0;
      letter-spacing: 0.4rem;
      font-family: 'Rafika', sans-serif;
    }
  }

  .links {
    display: flex;
    gap: 1rem;
    font-family: 'Rafika', sans-serif;
    color: lightgray;
  }
}
</style>
