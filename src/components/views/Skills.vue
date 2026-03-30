<template>
  <section class="max-w-[1440px] mx-auto px-12 mb-40 pt-20">
    <!-- Header -->
    <div class="mb-20">
      <h2 class="text-[clamp(3.5rem,8vw,5.5rem)] font-black tracking-tighter text-primary uppercase leading-none">
        TOOLSET
      </h2>
      <div class="h-[1px] w-full bg-primary mt-8"></div>
    </div>

    <!-- Toolset Columns -->
    <div class="grid grid-cols-12 gap-8 mb-40">
      <div v-for="(category, index) in toolset" :key="category.title" 
           class="col-span-6 md:col-span-3 border-l border-outline-variant/30 pl-8 transition-all hover:border-primary group">
        <span class="font-label text-[0.625rem] tracking-[0.2em] uppercase text-secondary/40 group-hover:text-primary transition-colors">
          {{ category.label }}
        </span>
        <ul class="mt-8 flex flex-col gap-3">
          <li v-for="tool in category.tools" :key="tool" 
              class="font-headline font-bold text-[0.875rem] uppercase text-primary tracking-tight">
            {{ tool }}
          </li>
        </ul>
      </div>
    </div>

    <!-- Next Step Banner (Red Box) -->
    <div class="bg-[#c00] py-28 px-12 text-center text-white relative overflow-hidden group">
      <div class="relative z-10">
        <span class="font-label text-[0.6875rem] tracking-[0.3em] uppercase opacity-70 mb-8 block">PRÓXIMO PASO</span>
        <h2 class="text-[clamp(2.5rem,7vw,5.5rem)] font-black leading-none tracking-tighter uppercase mb-14">
          CONSTRUIR EL FUTURO.
        </h2>
        <a 
          href="#contact" 
          class="inline-block bg-white text-primary px-12 py-5 font-headline font-bold text-[0.6875rem] uppercase tracking-widest hover:scale-105 hover:bg-surface-dim transition-all duration-300"
        >
          COMENZAR UN PROYECTO
        </a>
      </div>
      <!-- Subtle Texture or Animation space -->
      <div class="absolute inset-0 bg-black/5 opacity-0 group-hover:opacity-100 transition-opacity"></div>
    </div>
  </section>
</template>

<script setup>
const toolset = [
  {
    label: 'DISEÑO',
    tools: ['FIGMA', 'WORDPRESS', 'E-COMMERCE', 'ADOBE CC']
  },
  {
    label: 'DESARROLLO',
    tools: ['VUE 3', 'JAVASCRIPT', 'PYTHON', 'MYSQL', 'HTML5 / CSS3']
  },
  {
    label: 'METODOLOGÍA',
    tools: ['SCRUM', 'AGILE', 'USER TESTING', 'PRIORIZACIÓN']
  },
  {
    label: 'OFICINA',
    tools: ['TRELLO', 'NOTION', 'SLACK', 'VS CODE']
  }
]
</script>
