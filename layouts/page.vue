<template>
  <div class="bg-[#3a3a3a] text-white w-full h-full relative p-10">
    <!-- 绝对定位，完全贴紧最左侧 top-10 left-0 -->
    <div class="absolute top-10 left-0 bg-[#e65176] w-8 h-10" style="clip-path: polygon(0 0, 100% 0, 60% 100%, 0 100%);"></div>
    
    <div class="flex items-center mb-12">
      <!-- 原本的粉色块移走了，这里直接显示 > 和标题 -->
      <span class="text-[#8ae28a] text-4xl font-bold mr-4">></span>
      <h1 class="text-[#eab308] text-4xl font-bold tracking-wider"><slot name="header" /></h1>
      
      <!-- 顶部右侧 Logo -->
      <img src="/logo.png" class="absolute right-10 top-10 h-10 object-contain" alt="logo" />
    </div>
    <!-- 内容区域 -->
    <div class="px-8 text-xl">
      <slot />
    </div>
    <BottomBar />
  </div>
</template>