<template>
  <footer id="contact" class="bg-background pt-20 pb-12 mt-40">
    <div class="max-w-[1440px] mx-auto px-12">
      <!-- Top Border Wall -->
      <div class="h-[2px] w-full bg-primary mb-24"></div>

      <!-- Main Footer Content -->
      <div class="grid grid-cols-12 gap-8 items-start relative mb-40">
        <div class="col-span-12 md:col-span-6 relative z-10">
          <h2 class="text-[clamp(1.5rem,5vw,3rem)] font-black tracking-tighter uppercase text-primary mb-8 leading-tight">
            ¿TIENES UN PROYECTO<br/>EN MENTE?
          </h2>
          <a 
            class="inline-block bg-primary text-white border border-primary px-12 py-5 font-headline font-bold text-[0.6875rem] uppercase tracking-widest hover:bg-transparent hover:text-primary transition-all duration-300"
            href="mailto:hernandezcruz.gabrielosmin@gmail.com"
          >
            INICIAR CONVERSACIÓN
          </a>
        </div>

        <!-- Faint Background Text -->
        <div class="absolute right-0 top-1/2 -translate-y-1/2 opacity-[0.03] pointer-events-none select-none">
          <span class="text-[12rem] font-black tracking-tighter uppercase leading-none">ARCHIVE</span>
        </div>
      </div>

      <!-- Bottom Utility Bar -->
      <div class="flex flex-col md:flex-row justify-between items-center md:items-end gap-10 pt-12 border-t border-outline-variant/10">
        <div class="w-full md:w-auto text-center md:text-left">
          <p class="font-headline font-medium text-[0.625rem] tracking-widest uppercase text-secondary/60">
            © 2026 DISEÑADO POR Gabriel Hernández. TODOS LOS DERECHOS RESERVADOS.
          </p>
        </div>

        <div class="flex flex-wrap justify-center md:justify-end gap-10">
          <a v-for="link in socialLinks" :key="link.name" :href="link.href" target="_blank"
             class="font-headline font-bold text-[0.6875rem] tracking-widest uppercase text-secondary hover:text-primary-fixed transition-all duration-300 relative group">
            {{ link.name }}
            <span class="absolute left-0 bottom-[-4px] w-full h-[1px] bg-secondary/30 group-hover:bg-primary-fixed transition-colors"></span>
          </a>
        </div>
      </div>
    </div>
  </footer> 
</template>

<script setup>
const socialLinks = [
  { name: 'INSTAGRAM', href: '#' },
  { name: 'LINKEDIN', href: 'https://www.linkedin.com/in/gabriel-hernandez-044b471b6' },
  { name: 'GITHUB', href: 'https://github.com/yggabo' },
  { name: 'EMAIL', href: 'mailto:hernandezcruz.gabrielosmin@gmail.com' }
]
</script>
