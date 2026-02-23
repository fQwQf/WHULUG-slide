<template>
  <div class="bg-[#333] text-white w-full h-full relative overflow-hidden">
    <!-- 左侧背景图 (你可以通过 props 替换图片) -->
    <div class="absolute inset-0 w-3/5 h-full bg-cover bg-center" style="background-image: url('https://images.unsplash.com/photo-1473625247510-8ceb1760943f?auto=format&fit=crop&w=1920&q=80')"></div>
    <!-- 右侧深灰色斜切遮罩 -->
    <div class="absolute inset-0 bg-[#3a3a3a]" style="clip-path: polygon(55% 0, 100% 0, 100% 100%, 35% 100%);"></div>
    
    <!-- 右上角企鹅/小鸟 Logo 占位 -->
    <div class="absolute top-6 right-8 text-5xl text-[#5da0d8] opacity-90 transform skew-x-[-15deg]">
      <carbon:linux />
    </div>

    <!-- 主标题区域 -->
    <div class="absolute top-1/3 right-0 w-[60%]">
       <!-- 粉色折带大标题 -->
       <div class="bg-[#e65176] text-white py-8 pl-16 pr-8 text-6xl font-bold tracking-widest relative" 
            style="clip-path: polygon(0 50%, 10% 0, 100% 0, 100% 100%, 10% 100%); margin-left: -10%;">
         <slot />
       </div>
       <!-- 蓝色小三角与副标题 -->
       <div class="mt-8 flex flex-col items-center pl-10 text-2xl text-gray-300">
         <div class="w-0 h-0 border-l-[12px] border-r-[12px] border-t-[18px] border-l-transparent border-r-transparent border-t-[#0088cc] mb-12"></div>
         <slot name="subtitle" />
       </div>
    </div>
  </div>
</template>