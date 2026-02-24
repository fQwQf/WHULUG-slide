<template>
  <div class="bg-[#3a3a3a] text-white w-full h-full relative p-10 flex flex-col">
    <!-- 顶部左侧装饰 -->
    <div class="absolute top-10 left-0 bg-[#e65176] w-8 h-10" style="clip-path: polygon(0 0, 100% 0, 60% 100%, 0 100%);"></div>
    
    <!-- Header -->
    <div class="flex items-center mb-5">
      <span class="text-[#8ae28a] text-3xl font-bold mr-3">></span>
      <h1 class="text-[#e5c07b] text-3xl font-bold tracking-wider"><slot name="header" /></h1>
      <img src="/logo.png" class="absolute right-10 top-10 h-8 object-contain" alt="logo" />
    </div>
    
    <!-- 两列内容区域 -->
    <div class="content-wrapper flex-1 flex px-6 overflow-hidden">
      <!-- 左列 -->
      <div class="left-col flex-1 pr-6 overflow-y-auto">
        <slot name="left" />
      </div>
      
      <!-- 分隔线 -->
      <div class="divider w-px bg-[#4a4a4a] opacity-50"></div>
      
      <!-- 右列 -->
      <div class="right-col flex-1 pl-6 overflow-y-auto">
        <slot name="right" />
      </div>
    </div>
    
    <BottomBar />
  </div>
</template>

<style scoped>
/* 列基础样式 */
.left-col, .right-col {
  font-size: 1rem;
  line-height: 1.6;
}

/* 段落间距 */
.left-col :deep(p), .right-col :deep(p) {
  margin-bottom: 0.75rem;
}

/* 标题样式 */
.left-col :deep(h1), .right-col :deep(h1) {
  font-size: 1.5rem;
  font-weight: bold;
  margin-bottom: 1rem;
  color: #e5c07b;
}

.left-col :deep(h2), .right-col :deep(h2) {
  font-size: 1.25rem;
  font-weight: bold;
  margin-top: 1rem;
  margin-bottom: 0.75rem;
  color: #e5c07b;
}

.left-col :deep(h3), .right-col :deep(h3) {
  font-size: 1.05rem;
  font-weight: bold;
  margin-top: 0.875rem;
  margin-bottom: 0.5rem;
  color: #8ae28a;
}

/* 列表样式 */
.left-col :deep(ul), .right-col :deep(ul) {
  margin-left: 1.25rem;
  margin-bottom: 0.875rem;
  list-style-type: disc;
}

.left-col :deep(ol), .right-col :deep(ol) {
  margin-left: 1.25rem;
  margin-bottom: 0.875rem;
  list-style-type: decimal;
}

.left-col :deep(li), .right-col :deep(li) {
  margin-bottom: 0.375rem;
}

/* 代码块样式 */
.left-col :deep(pre), .right-col :deep(pre) {
  background: #282c34;
  border-radius: 6px;
  padding: 0.875rem;
  margin: 0.875rem 0;
  overflow-x: auto;
  border-left: 3px solid #61afee;
  font-size: 0.85em;
}

.left-col :deep(code), .right-col :deep(code) {
  font-family: 'Fira Code', monospace;
}

/* 强制覆盖 Shiki 语法高亮颜色 */
.left-col :deep(pre code),
.left-col :deep(pre code span),
.left-col :deep(.shiki),
.left-col :deep(.shiki span),
.left-col :deep(.slidev-code-block),
.right-col :deep(pre code),
.right-col :deep(pre code span),
.right-col :deep(.shiki),
.right-col :deep(.shiki span),
.right-col :deep(.slidev-code-block) {
  color: #e2e4e8 !important;
}

/* 行内代码 */
.left-col :deep(:not(pre) > code), .right-col :deep(:not(pre) > code) {
  background: #3e4451;
  padding: 0.15em 0.35em;
  border-radius: 3px;
  color: #e5c07b;
  font-size: 0.9em;
}

/* 表格样式 */
.left-col :deep(table), .right-col :deep(table) {
  width: 100%;
  border-collapse: collapse;
  margin: 0.875rem 0;
  font-size: 0.9em;
}

.left-col :deep(th), .right-col :deep(th) {
  background: #3e4451;
  padding: 0.625rem;
  text-align: left;
  font-weight: bold;
  border-bottom: 2px solid #61afee;
}

.left-col :deep(td), .right-col :deep(td) {
  padding: 0.625rem;
  border-bottom: 1px solid #4a4a4a;
}

/* 引用块 */
.left-col :deep(blockquote), .right-col :deep(blockquote) {
  border-left: 3px solid #e65176;
  padding-left: 0.875rem;
  margin: 0.875rem 0;
  color: #b0b0b0;
  font-style: italic;
}

/* 强调文字 */
.left-col :deep(strong), .right-col :deep(strong) {
  color: #8ae28a;
  font-weight: bold;
}

/* 链接 */
.left-col :deep(a), .right-col :deep(a) {
  color: #61afee;
  text-decoration: none;
}

/* 分隔线 */
.divider {
  min-height: 100%;
}

/* 滚动条样式 */
.left-col::-webkit-scrollbar,
.right-col::-webkit-scrollbar {
  width: 6px;
}

.left-col::-webkit-scrollbar-thumb,
.right-col::-webkit-scrollbar-thumb {
  background: #4a4a4a;
  border-radius: 3px;
}

.left-col::-webkit-scrollbar-thumb:hover,
.right-col::-webkit-scrollbar-thumb:hover {
  background: #61afee;
}
</style>