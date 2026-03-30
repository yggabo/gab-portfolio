<script setup>
import Navigation from './components/layout/Navigation.vue'
import Footer from './components/layout/Footer.vue'
import HomeHero from './components/views/Home.vue'
import About from './components/views/About.vue'
import FeaturedProject from './components/views/FeaturedProject.vue'
import Skills from './components/views/Skills.vue'
import ProjectArchive from './components/views/ProjectArchive.vue'
</script>

<template>
  <div class="min-h-screen bg-background text-on-background selection:bg-primary-fixed selection:text-white">
    <!-- Grid Toggle -->
    <input class="hidden peer/grid" id="grid-toggle" type="checkbox"/>
    <div class="hidden peer-checked/grid:grid fixed inset-0 grid-cols-12 gap-8 px-12 z-[100] opacity-10 pointer-events-none">
      <div v-for="i in 12" :key="i" class="bg-primary h-full"></div>
    </div>

    <Navigation />
    
    <main>
      <HomeHero id="home" />
      <About id="about" />
      <FeaturedProject />
      <Skills id="skills" />
      <ProjectArchive id="archive" />
    </main>
    
    <Footer id="contact" />
  </div>
</template>

<style>
/* Global resets and typography handled in assets/main.css */
@import "./assets/main.css";

/* Custom smooth scroll and transitions */
html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

::selection {
  @apply bg-primary-fixed text-white;
}
</style>
