<template>
  <div class="group border-b border-foreground p-6 md:p-12 hover:bg-foreground hover:text-background transition-colors cursor-pointer">
    <div class="max-w-[1440px] mx-auto grid grid-cols-12 gap-8 items-center">
      <div class="col-span-12 md:col-span-1 text-sm font-black uppercase tracking-tight text-accent group-hover:text-background transition-colors">
        // {{ year }}
      </div>
      
      <div class="col-span-12 md:col-span-5 mb-8 md:mb-0">
        <h3 class="text-4xl md:text-6xl font-black uppercase tracking-[-0.05em] leading-none mb-4 group-hover:text-background transition-colors">
          {{ name }}
        </h3>
        <span class="text-xs font-black uppercase tracking-tighter text-foreground group-hover:text-background transition-colors">
          {{ category }}
        </span>
      </div>
      
      <div class="col-span-12 md:col-span-6 overflow-hidden border border-foreground">
        <img :src="image" :alt="name" class="w-full h-auto object-cover grayscale brightness-110 contrast-125 saturate-0 group-hover:grayscale-0 group-hover:brightness-100 group-hover:contrast-100 group-hover:saturate-100 transition-all duration-500 hover:scale-[1.05]" />
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  name: String,
  category: String,
  year: String,
  image: {
    type: String,
    default: 'https://via.placeholder.com/800x450'
  }
})
</script>
