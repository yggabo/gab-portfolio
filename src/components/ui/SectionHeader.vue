<template>
  <header class="px-6 md:px-12 py-12 md:py-24 border-b border-foreground">
    <div class="max-w-[1440px] mx-auto grid grid-cols-12 gap-8 items-start">
      <div class="col-span-12 md:col-span-3 mb-8 md:mb-0">
        <span class="text-sm font-black uppercase tracking-tight text-accent block mb-4">// {{ number }}</span>
        <div class="h-[1px] w-full bg-foreground md:max-w-[120px]"></div>
      </div>
      <div class="col-span-12 md:col-span-9">
        <h2 class="text-7xl md:text-9xl lg:text-[10vw] font-black uppercase tracking-[-0.05em] leading-[0.85]">
          {{ title }}
        </h2>
      </div>
    </div>
  </header>
</template>

<script setup>
const props = defineProps({
  title: {
    type: String,
    required: true
  },
  number: {
    type: String,
    default: '01'
  }
})
</script>
