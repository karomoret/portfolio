<script setup lang="ts">
import Home from '../pages/Home.vue'
import About from '../pages/About.vue'
import Contact from '../pages/Contact.vue'
import Media from '../pages/Media.vue'
import { type Component, computed, ref } from 'vue'
import Nav from '@/components/Nav.vue'

const routes: { [key: string]: Component } = {
  '/': Home,
  '/about': About,
  '/contact': Contact,
  '/media': Media,
}

const currentPath = ref(window.location.hash)

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
})

const currentView = computed(() => {
  return routes[currentPath.value.substring(1)]
})
</script>

<template>
  <Nav />
  <component :is="currentView"></component>
</template>

<style scoped></style>
