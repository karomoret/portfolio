<script setup lang="ts">
import Home from '../pages/Home.vue'
import About from '../pages/About.vue'
import Contact from '../pages/Contact.vue'
import Media from '../pages/Media.vue'
import { type Component, computed } from 'vue'
import Nav from '@/components/Nav.vue'

const routes: { [key: string]: Component } = {
  '/': Home,
  '/about': About,
  '/contact': Contact,
  '/media': Media,
}

const currentView = computed(() => {
  let pathname = window.location.pathname
  if (routes[pathname]) return routes[pathname]
  window.location.pathname = '/'
  return routes['/']
})
</script>

<template>
  <Nav v-if="currentView != routes['/']" />
  <component :is="currentView"></component>
</template>

<style>
html {
  font-family: sans-serif;
}
body {
  margin: 0;
}
</style>
