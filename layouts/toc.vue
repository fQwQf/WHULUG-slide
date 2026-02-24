<template>
  <div class="bg-[#3a3a3a] text-white w-full h-full relative flex flex-col items-center justify-center overflow-hidden">
    <div class="flex items-center mb-8">
      <img src="/logo.png" class="h-12 mr-4 object-contain" alt="logo" />
      <h1 class="text-[#e5c07b] text-3xl font-bold tracking-widest">目录</h1>
    </div>

    <div 
      ref="tocContainer" 
      class="toc-container flex flex-col gap-4 items-center w-full px-8"
      :class="columnClass"
    >
      <slot />
    </div>
    
    <BottomBar />
  </div>
</template>

<script setup>
import { ref, onMounted, computed } from 'vue'

const props = defineProps({
  start: {
    type: Number,
    default: 1
  }
})

const tocContainer = ref(null)
const itemCount = ref(0)

const columnClass = computed(() => {
  if (itemCount.value <= 5) return 'single-column'
  if (itemCount.value <= 10) return 'two-columns'
  return 'three-columns'
})

onMounted(() => {
  if (tocContainer.value) {
    const lis = tocContainer.value.querySelectorAll('li')
    itemCount.value = lis.length
    
    // 为每个 li 添加编号包装器
    lis.forEach((li, index) => {
      const number = String(props.start + index).padStart(2, '0')
      const numberSpan = document.createElement('span')
      numberSpan.className = 'toc-number'
      numberSpan.innerHTML = `<span class="toc-arrow">></span><span class="toc-digit">${number}</span>`
      li.insertBefore(numberSpan, li.firstChild)
    })
  }
})
</script>

<style>
.toc-container ul {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  flex-direction: column;
  gap: 1rem;
  align-items: center;
  width: 100%;
}

/* 单列布局 */
.toc-container.single-column ul {
  font-size: 1.5rem;
}

/* 两列布局 */
.toc-container.two-columns ul {
  display: grid;
  grid-template-rows: repeat(5, auto);
  grid-auto-flow: column;
  gap: 0.75rem 4rem;
  align-items: start;
  justify-items: center;
  width: 100%;
  max-width: 100%;
  font-size: 1.25rem;
  padding: 0 2rem;
}

.toc-container.two-columns li {
  align-items: center;
  width: 100%;
  text-align: center;
}

/* 三列布局 */
.toc-container.three-columns ul {
  display: grid;
  grid-template-rows: repeat(4, auto);
  grid-auto-flow: column;
  gap: 0.5rem 2rem;
  align-items: start;
  justify-items: center;
  width: 100%;
  max-width: 100%;
  font-size: 1rem;
  padding: 0 1.5rem;
}

.toc-container.three-columns li {
  align-items: center;
  width: 100%;
  text-align: center;
}

.toc-container li {
  display: flex;
  flex-direction: column;
  align-items: center;
  line-height: 1.3;
}

.toc-container li .toc-number {
  display: flex;
  align-items: center;
  gap: 0.25em;
  margin-bottom: 0.125rem;
  font-size: 0.75em;
  font-weight: bold;
  font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace;
}

.toc-container li .toc-arrow {
  color: #ce5bd8;
}

.toc-container li .toc-digit {
  color: #61afee;
}

.toc-container li p {
  letter-spacing: 0.05em;
  color: white !important;
  margin: 0;
  line-height: 1.3;
}

/* 响应式字体大小 */
.toc-container.single-column li p {
  font-size: 1em !important;
}

.toc-container.two-columns li p {
  font-size: 0.9em !important;
}

.toc-container.three-columns li p {
  font-size: 0.85em !important;
}
</style>