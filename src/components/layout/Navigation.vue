<template>
  <header class="fixed top-0 left-0 right-0 z-50 bg-background border-b border-outline-variant/30">
    <nav class="flex justify-between items-center w-full max-w-[1440px] mx-auto px-12 py-8">
      <!-- Logo (Using primary name from resume) -->
      <div class="flex items-center gap-6">
        <div class="text-2xl font-black tracking-tighter text-primary uppercase select-none leading-none">
          GABRIEL<br/>
          <span class="text-outline-variant/40">OSMIN</span>
        </div>
        <div class="hidden lg:block h-10 w-[1px] bg-outline-variant/30"></div>
        <div class="hidden lg:block font-label text-[0.625rem] tracking-[0.3em] uppercase text-secondary/60 leading-tight">
          ESPECIALISTA<br/>FRONTEND
        </div>
      </div>

      <!-- Navigation Links -->
      <div class="hidden md:flex gap-12 items-center">
        <a 
          v-for="link in navLinks" 
          :key="link.name"
          :href="link.href"
          class="font-headline font-bold tracking-[-0.04em] uppercase text-[0.6875rem] transition-all duration-150 pb-1 border-b-2"
          :class="[
            activeSection === link.name.toLowerCase() 
              ? 'text-primary border-primary-fixed' 
              : 'text-secondary border-transparent hover:text-primary-fixed hover:border-primary-fixed/30'
          ]"
          @click="setActive(link.name.toLowerCase())"
        >
          {{ link.name }}
        </a>
      </div>

      <!-- Contact Button -->
      <div>
        <a 
          href="#contact" 
          class="font-headline font-bold tracking-[-0.04em] uppercase text-[0.6875rem] text-primary border border-primary px-8 py-3 rounded-none hover:bg-primary hover:text-white transition-all duration-200"
        >
          CONTACTO
        </a>
      </div>
    </nav>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const activeSection = ref('home')

const navLinks = [
  { name: 'INICIO', href: '#home' },
  { name: 'PERFIL', href: '#about' },
  { name: 'HABILIDADES', href: '#skills' },
  { name: 'PROYECTOS', href: '#projects' }
]

const setActive = (section) => {
  activeSection.value = section
}
</script>
