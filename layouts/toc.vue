<template>
  <div class="bg-[#3a3a3a] text-white w-full h-full relative flex flex-col items-center justify-center">
    <div class="flex items-center mb-12">
      <!-- 使用图片 Logo -->
      <img src="/logo.png" class="h-16 mr-6 object-contain" alt="logo" />
      <h1 class="text-[#eab308] text-5xl font-bold tracking-widest">目录</h1>
    </div>
    <!-- 目录列表容器 -->
    <div class="flex flex-col gap-2 items-center w-full">
      <slot />
    </div>
    <BottomBar />
  </div>
</template>