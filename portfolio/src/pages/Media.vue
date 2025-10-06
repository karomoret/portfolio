<script setup lang="ts">
import config from '../config/config.json'
import { ref } from 'vue'
const totalPaintings = config.media.length
let currentPainting = ref(1)
</script>

<template>
  <div class="container">
    <span class="gallery">
      <img v-for="painting in config.media" :src="'/images/' + painting.image" alt="Painting" />
    </span>
  </div>
</template>

<style scoped lang="scss">
.container {
  padding: 1rem;

  .gallery {
    height: 100%;
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    //flex-direction: column;
    justify-content: space-evenly;
    gap: 1rem;

    img {
      max-width: 80%;
      object-fit: contain;
      //max-width: 300px;
    }
  }
}
</style>
