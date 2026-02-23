<template>
  <div class="bg-[#3a3a3a] text-gray-300 w-full h-full relative p-12 flex flex-col items-center justify-center">
    <h1 class="text-[#f17a94] font-mono tracking-widest text-4xl mb-8 font-light">
      DISCLAIMER
    </h1>
    <div class="text-lg leading-loose text-center opacity-90">
      <slot />
    </div>
    <!-- 注入状态栏 (警告色) -->
    <BottomBar mode="DISCLAIMER" modeClass="bg-[#f17a94] text-[#222]" dateClass="bg-[#f17a94] text-[#222]" />
  </div>
</template>