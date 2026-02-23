<template>
  <div class="bg-[#3a3a3a] text-white w-full h-full relative p-10 flex flex-col justify-center items-center">
    
    <!-- 顶部左侧装饰 (贴紧左侧) -->
    <div class="absolute top-10 left-0 flex items-center">
       <div class="bg-[#e65176] w-8 h-10 mr-6" style="clip-path: polygon(0 0, 100% 0, 60% 100%, 0 100%);"></div>
       <img src="/logo.png" class="h-10 object-contain" alt="logo" />
    </div>
    
    <!-- 核心排版：使用 1fr-auto-auto-1fr 的网格系统，确保绝对视觉居中 -->
    <div class="grid w-full mb-8" style="grid-template-columns: 1fr auto auto 1fr;">
      
      <!-- 第一列：01 -->
      <div class="col-start-2 flex justify-center items-end">
        <span class="text-[#5da0d8] text-9xl font-bold leading-none"><slot name="number" /></span>
      </div>
      
      <!-- 第二列：标题 -->
      <div class="col-start-3 flex items-end pl-8 pb-3">
        <span class="text-white text-5xl font-bold tracking-widest"><slot name="title" /></span>
      </div>

      <!-- 第一列的正下方：PART ONE -->
      <div class="col-start-2 flex justify-center mt-6">
        <span class="text-[#8ae28a] font-mono tracking-widest text-2xl"><slot name="subtitle" /></span>
      </div>
      
    </div>
    
    <BottomBar />
  </div>
</template>