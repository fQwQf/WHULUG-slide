<template>
  <div class="bg-[#3a3a3a] text-white w-full h-full relative p-10 flex flex-col">
    <!-- 顶部左侧装饰 -->
    <div class="absolute top-10 left-0 bg-[#e65176] w-8 h-10" style="clip-path: polygon(0 0, 100% 0, 60% 100%, 0 100%);"></div>
    
    <!-- Header -->
    <div class="flex items-center mb-6">
      <span class="text-[#8ae28a] text-3xl font-bold mr-3">></span>
      <h1 class="text-[#e5c07b] text-3xl font-bold tracking-wider"><slot name="header" /></h1>
      <img src="/logo.png" class="absolute right-10 top-10 h-8 object-contain" alt="logo" />
    </div>
    
    <!-- 内容区域 -->
    <div class="content-area flex-1 px-8 overflow-y-auto">
      <slot />
    </div>
    
    <BottomBar />
  </div>
</template>

<style scoped>
/* 内容区域基础样式 */
.content-area {
  font-size: 1.1rem;
  line-height: 1.6;
}

/* 段落间距 */
.content-area :deep(p) {
  margin-bottom: 0.875rem;
}

/* 标题样式 */
.content-area :deep(h1) {
  font-size: 1.75rem;
  font-weight: bold;
  margin-bottom: 1.25rem;
  color: #e5c07b;
}

.content-area :deep(h2) {
  font-size: 1.35rem;
  font-weight: bold;
  margin-top: 1.25rem;
  margin-bottom: 0.875rem;
  color: #e5c07b;
}

.content-area :deep(h3) {
  font-size: 1.15rem;
  font-weight: bold;
  margin-top: 1rem;
  margin-bottom: 0.625rem;
  color: #8ae28a;
}

/* 列表样式 */
.content-area :deep(ul) {
  margin-left: 1.25rem;
  margin-bottom: 0.875rem;
  list-style-type: disc;
}

.content-area :deep(ol) {
  margin-left: 1.25rem;
  margin-bottom: 0.875rem;
  list-style-type: decimal;
}

.content-area :deep(li) {
  margin-bottom: 0.375rem;
}

/* 代码块样式 */
.content-area :deep(pre) {
  background: #282c34;
  border-radius: 6px;
  padding: 0.875rem;
  margin: 0.875rem 0;
  overflow-x: auto;
  border-left: 3px solid #61afee;
}

.content-area :deep(code) {
  font-family: 'Fira Code', monospace;
  font-size: 0.9em;
}

/* 强制覆盖 Shiki 语法高亮颜色 */
.content-area :deep(pre code),
.content-area :deep(pre code span),
.content-area :deep(.shiki),
.content-area :deep(.shiki span),
.content-area :deep(.slidev-code-block) {
  color: #e2e4e8 !important;
}

/* 行内代码 */
.content-area :deep(:not(pre) > code) {
  background: #3e4451;
  padding: 0.2em 0.4em;
  border-radius: 4px;
  color: #e5c07b;
}

/* 表格样式 */
.content-area :deep(table) {
  width: 100%;
  border-collapse: collapse;
  margin: 1rem 0;
  font-size: 0.95em;
}

.content-area :deep(th) {
  background: #3e4451;
  padding: 0.75rem;
  text-align: left;
  font-weight: bold;
  border-bottom: 2px solid #61afee;
}

.content-area :deep(td) {
  padding: 0.75rem;
  border-bottom: 1px solid #4a4a4a;
}

.content-area :deep(tr:hover) {
  background: rgba(97, 175, 238, 0.1);
}

/* 引用块 */
.content-area :deep(blockquote) {
  border-left: 4px solid #e65176;
  padding-left: 1rem;
  margin: 1rem 0;
  color: #b0b0b0;
  font-style: italic;
}

/* 强调文字 */
.content-area :deep(strong) {
  color: #8ae28a;
  font-weight: bold;
}

/* 链接 */
.content-area :deep(a) {
  color: #61afee;
  text-decoration: none;
}

.content-area :deep(a:hover) {
  text-decoration: underline;
}

/* 水平线 */
.content-area :deep(hr) {
  border: none;
  border-top: 1px solid #4a4a4a;
  margin: 2rem 0;
}
</style>