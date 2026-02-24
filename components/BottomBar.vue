<script setup>
defineProps({
  mode: { type: String, default: 'main' },
  modeClass: { type: String, default: 'bg-[#8ae28a] text-[#222]' },
  dateClass: { type: String, default: 'bg-[#8ae28a] text-[#222]' },
  filepath: { type: String, default: '/home/WHULUG/滚滚长江东逝水.pptx' },
  // 直接使用 JS 原生方法获取当日日期
  // 如果想指定某一天，替换即可
  date: { 
    type: String, 
    default: () => {
      const d = new Date()
      return `${d.getFullYear()}-${String(d.getMonth() + 1).padStart(2, '0')}-${String(d.getDate()).padStart(2, '0')}`
    }
  }
})
</script>

<template>
  <div class="absolute bottom-0 left-0 w-full h-[26px] bg-[#666] flex justify-between items-center text-[13px] font-mono z-50">

    <div class="flex h-full items-center">
      <div :class="['px-3 h-full flex items-center font-bold tracking-wider', modeClass]">
        <carbon:branch class="mr-2" v-if="mode === 'main'" />
        <carbon:warning-filled class="mr-2" v-if="mode === 'DISCLAIMER'" />
        {{ mode }}
      </div>
      <div class="px-4 h-full flex items-center bg-[#444] text-gray-300 tracking-wider">
        - WHULUG -
      </div>
      <div class="px-4 h-full flex items-center bg-[#666] text-gray-200">
        <carbon:folder class="mr-2" /> {{ filepath }}
      </div>
    </div>

    <div :class="['px-4 h-full flex items-center font-bold', dateClass]">
      <carbon:calendar class="mr-2" /> {{ date }}
    </div>
  </div>
</template>