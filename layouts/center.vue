<template>
  <div class="bg-[#3a3a3a] text-white w-full h-full relative p-10 flex flex-col">
    <!-- 顶部左侧装饰 -->
    <div class="absolute top-10 left-0 bg-[#e65176] w-8 h-10" style="clip-path: polygon(0 0, 100% 0, 60% 100%, 0 100%);"></div>
    
    <!-- Header -->
    <div class="flex items-center mb-6">
      <span class="text-[#8ae28a] text-3xl font-bold mr-3">></span>
      <h1 class="text-[#e5c07b] text-3xl font-bold tracking-wider"><slot name="header" /></h1>
      <img src="./logo.png" class="absolute right-10 top-10 h-8 object-contain" alt="logo" />
    </div>
    
    <!-- 居中内容区域 -->
    <div class="flex-1 flex justify-center items-center">
      <div class="center-content text-center max-w-3xl">
        <slot />
      </div>
    </div>
    
    <BottomBar />
  </div>
</template>

<style scoped>
/* 居中内容基础样式 */
.center-content {
  font-size: 1.2rem;
  line-height: 1.7;
}

/* 标题样式 - 居中且更大 */
.center-content :deep(h1) {
  font-size: 2.5rem;
  font-weight: bold;
  margin-bottom: 1rem;
  color: #e5c07b;
}

.center-content :deep(h2) {
  font-size: 1.5rem;
  font-weight: normal;
  margin-bottom: 2rem;
  color: #8ae28a;
  opacity: 0.9;
}

.center-content :deep(h3) {
  font-size: 1.25rem;
  font-weight: bold;
  margin-top: 1.5rem;
  margin-bottom: 0.75rem;
  color: #e2e4e8;
}

/* 段落 */
.center-content :deep(p) {
  margin-bottom: 1rem;
}

/* 列表样式 */
.center-content :deep(ul) {
  margin-left: 1.5rem;
  margin-bottom: 1rem;
  text-align: left;
  display: inline-block;
  list-style-type: disc;
}

.center-content :deep(ol) {
  margin-left: 1.5rem;
  margin-bottom: 1rem;
  text-align: left;
  display: inline-block;
  list-style-type: decimal;
}

.center-content :deep(li) {
  margin-bottom: 0.5rem;
}

/* 强调文字 */
.center-content :deep(strong) {
  color: #8ae28a;
  font-weight: bold;
}

/* 代码块样式 */
.center-content :deep(pre) {
  background: #282c34;
  border-radius: 6px;
  padding: 1rem;
  margin: 1rem auto;
  overflow-x: auto;
  border-left: 3px solid #61afee;
  text-align: left;
  max-width: 100%;
}

.center-content :deep(code) {
  font-family: 'Fira Code', monospace;
  font-size: 0.9em;
}

.center-content :deep(pre code) {
  color: #e2e4e8 !important;
  background: transparent !important;
}

/* 行内代码 */
.center-content :deep(:not(pre) > code) {
  background: #3e4451;
  padding: 0.2em 0.4em;
  border-radius: 4px;
  color: #e5c07b;
}

/* 引用块 */
.center-content :deep(blockquote) {
  border-left: 3px solid #e65176;
  padding-left: 1rem;
  margin: 1rem auto;
  color: #b0b0b0;
  font-style: italic;
  text-align: left;
  max-width: 80%;
}

/* 链接 */
.center-content :deep(a) {
  color: #61afee;
  text-decoration: none;
}

/* 隐藏代码块滚动条 */
.center-content :deep(pre)::-webkit-scrollbar {
  display: none;
}

.center-content :deep(pre) {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
</style>