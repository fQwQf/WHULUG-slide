<script setup>
defineProps({
  background: {
    type: String,
    default: 'logo2.png'
  }
})
</script>

<template>
  <div class="bg-[#333] text-white absolute inset-0 overflow-hidden">
    
    <div class="absolute inset-0 w-[80%] h-full bg-cover bg-center" :style="{ backgroundImage: `url(${background})` }"></div>
    
    <div class="absolute inset-0 bg-black/40" style="clip-path: polygon(45% 0, 100% 0, 100% 100%, 25% 100%);"></div>
    
    <div class="absolute inset-0 bg-[#3a3a3a]" style="clip-path: polygon(50% 0, 100% 0, 100% 100%, 30% 100%);"></div>
    
    <div class="absolute top-8 right-10">
      <img src="/logo2.png" class="h-16 object-contain opacity-90" alt="logo" />
    </div>

    <div class="absolute top-1/3 right-0 w-[60%] flex flex-col justify-center">
       
       <div class="bg-[#e65176] text-white py-6 pl-12 pr-4 text-6xl font-bold tracking-widest relative flex items-center justify-center" 
            style="clip-path: polygon(0 50%, 10% 0, 100% 0, 100% 100%, 10% 100%); margin-left: -10%;">
         <slot />
       </div>
       
         <div class="mt-8 flex flex-col items-center justify-center w-full text-2xl text-gray-300 tracking-wider" style="margin-left: -5%;">
          <div class="w-0 h-0 border-l-[12px] border-r-[12px] border-t-[18px] border-l-transparent border-r-transparent border-t-[#0088cc] mb-12"></div>
          <slot name="subtitle" />
        </div>

    </div>
  </div>
</template>

<style scoped>
:deep(h1) {
  margin: 0 !important;
  padding: 0 !important;
  border: none !important;
  line-height: 1.2 !important;
  text-align: center !important;
  width: 100% !important;
}
</style>