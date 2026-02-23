<template>
  <div class="bg-[#333] text-white absolute inset-0 overflow-hidden">
    
    <!-- 1. 最底层：左侧背景图 -->
    <div class="absolute inset-0 w-[80%] h-full bg-cover bg-center" style="background-image: url('https://images.unsplash.com/photo-1473625247510-8ceb1760943f?auto=format&fit=crop&w=1920&q=80')"></div>
    
    <!-- 2. 中间层：半透明缓冲区 -->
    <div class="absolute inset-0 bg-black/40" style="clip-path: polygon(45% 0, 100% 0, 100% 100%, 25% 100%);"></div>
    
    <!-- 3. 顶层遮罩：右侧深灰色纯色块 -->
    <div class="absolute inset-0 bg-[#3a3a3a]" style="clip-path: polygon(50% 0, 100% 0, 100% 100%, 30% 100%);"></div>
    
    <!-- 右上角 Logo -->
    <div class="absolute top-8 right-10">
      <img src="/logo.png" class="h-16 object-contain opacity-90" alt="logo" />
    </div>

    <!-- 主标题区域 -->
    <div class="absolute top-1/3 right-0 w-[60%] flex flex-col justify-center">
       
       <!-- 粉色折带大标题 (加入了 justify-center 并微调了 padding 使其视觉居中) -->
       <div class="bg-[#e65176] text-white py-6 pl-12 pr-4 text-6xl font-bold tracking-widest relative flex items-center justify-center" 
            style="clip-path: polygon(0 50%, 10% 0, 100% 0, 100% 100%, 10% 100%); margin-left: -10%;">
         <slot />
       </div>
       
       <!-- 蓝色小三角与副标题：同样设置居中，并保持与上方文字相同的视觉中轴线 -->
       <div class="mt-8 flex flex-col items-center justify-center w-full pl-[5%] text-2xl text-gray-300 tracking-wider">
         <div class="w-0 h-0 border-l-[12px] border-r-[12px] border-t-[18px] border-l-transparent border-r-transparent border-t-[#0088cc] mb-12"></div>
         <slot name="subtitle" />
       </div>

    </div>
  </div>
</template>

<style scoped>
/* 强制 Slidev 渲染出的 H1 标签文字居中并占满宽度 */
:deep(h1) {
  margin: 0 !important;
  padding: 0 !important;
  border: none !important;
  line-height: 1.2 !important;
  text-align: center !important;
  width: 100% !important;
}
</style>