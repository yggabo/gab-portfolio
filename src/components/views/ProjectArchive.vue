<template>
  <section id="projects" class="max-w-[1440px] mx-auto px-12 mb-40 pt-20">
    <div class="grid grid-cols-12 gap-8 mb-20 items-end">
      <div class="col-span-12 md:col-span-8">
        <h2 class="text-display-lg text-primary uppercase leading-none tracking-tighter">
          ARCHIVO DE<br/>
          <span class="text-secondary/30">PROYECTOS</span>
        </h2>
      </div>
      <div class="col-span-12 md:col-span-4 md:text-right">
        <p class="font-label text-[0.6875rem] tracking-widest uppercase text-secondary">PROYECTOS SELECCIONADOS 2024—2026</p>
      </div>
    </div>

    <!-- Editorial Project Grid -->
    <div class="grid grid-cols-12 gap-12">
      <div 
        v-for="(project, index) in projects" 
        :key="project.id"
        class="col-span-12 md:col-span-6 lg:col-span-4 group cursor-pointer"
        :class="index % 3 === 1 ? 'lg:-mt-20' : ''"
      >
        <div class="aspect-editorial bg-surface-dim overflow-hidden mb-6 relative">
          <div class="absolute inset-0 bg-primary/0 group-hover:bg-primary/5 transition-all duration-500"></div>
          <!-- Project image placeholder -->
          <div class="w-full h-full flex items-center justify-center text-outline-variant group-hover:text-primary-fixed transition-colors">
            <span class="text-[4rem] font-black opacity-10">{{ index + 1 }}</span>
          </div>
        </div>
        <div class="flex justify-between items-start">
          <div>
            <h3 class="font-headline font-bold text-xl uppercase text-primary mb-1 tracking-tighter group-hover:text-primary-fixed transition-colors">
              {{ project.title }}
            </h3>
            <p class="font-label text-[0.625rem] tracking-[0.2em] uppercase text-secondary/60">{{ project.category }}</p>
          </div>
          <span class="font-headline font-bold text-[0.6875rem] text-primary group-hover:translate-x-2 transition-transform duration-300">→</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  { id: 1, title: 'Sistema de Gestión E-commerce', category: 'DEVELOPMENT' },
  { id: 2, title: 'Identidad Visual Digital', category: 'BRANDING' },
  { id: 3, title: 'Plataforma de Educación', category: 'WEB DESIGN' },
  { id: 4, title: 'Optimización de Rendimiento', category: 'TECHNICAL' },
  { id: 5, title: 'Interfaz de Usuario Moderna', category: 'UI/UX' },
  { id: 6, title: 'Arquitectura de Datos', category: 'BACKEND' }
]
</script>
