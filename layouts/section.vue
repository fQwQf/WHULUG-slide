<template>
  <div class="bg-[#3a3a3a] text-white w-full h-full relative p-10 flex flex-col justify-center items-center">
    
    <div class="absolute top-10 left-0 flex items-center">
       <div class="bg-[#e65176] w-8 h-10 mr-6" style="clip-path: polygon(0 0, 100% 0, 60% 100%, 0 100%);"></div>
       <img src="./logo.png" class="h-10 object-contain" alt="logo" />
    </div>
    
    <div class="section-content grid w-full mb-8 items-center" style="grid-template-columns: 1fr auto auto 1fr; gap: 2rem;">
      
      <div class="col-start-2 flex flex-col items-center justify-center">
        <span class="section-number text-[#61afee] font-bold leading-none">{{ number }}</span>
        <span class="section-subtitle text-[#8ae28a] font-mono tracking-widest mt-2">PART {{ partLetter }}</span>
      </div>
      
      <div class="col-start-3 flex items-center justify-center">
        <span class="section-title text-white text-5xl font-bold tracking-widest"><slot /></span>
      </div>
      
    </div>
    
    <BottomBar />
  </div>
</template>

<script setup>
import { computed, getCurrentInstance } from 'vue'

const props = defineProps({
  number: {
    type: String,
    default: '01'
  }
})

// 从全局 frontmatter 获取 offset，默认为 1（即 01->A）
const instance = getCurrentInstance()
const sectionOffset = computed(() => {
  // 尝试从全局 $slidev 获取配置
  const globalOffset = instance?.appContext?.config?.globalProperties?.$slidev?.configs?.sectionOffset
  return globalOffset !== undefined ? globalOffset : 1
})

// 根据序号生成 PART 字母
// offset=1: 01->A, 02->B, 03->C
// offset=0: 00->A, 01->B, 02->C
const partLetter = computed(() => {
  const num = parseInt(props.number)
  if (isNaN(num)) return 'A'
  const adjustedNum = num - sectionOffset.value
  if (adjustedNum < 0 || adjustedNum > 25) return 'A'
  return String.fromCharCode(65 + adjustedNum)
})
</script>

<style>
.section-number {
  font-size: 3rem;
}

.section-subtitle {
  font-size: 1.25rem;
}
</style>