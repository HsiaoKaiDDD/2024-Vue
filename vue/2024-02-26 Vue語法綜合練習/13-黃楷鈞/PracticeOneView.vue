
<!-- 輸入  http://localhost:5173/practice-one -->
<script>
import vueLogo from '@/assets/images/logo.svg';

export default {/*都沒更動*/
  data() {
    return {
      vueLogo,
      TabPage: 1,
    };
  },
};
</script>

<template>

  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <button type="button" class="nav-btn" :class="{ 'active': TabPage === 1 }" @click="TabPage = 1">Vue</button>
      <button type="button" class="nav-btn" :class="{ 'active': TabPage === 2 }" @click="TabPage = 2">編號</button>
      <button type="button" class="nav-btn" :class="{ 'active': TabPage === 3 }" @click="TabPage = 3">姓名</button>
      <button type="button" class="nav-btn" :class="{ 'active': TabPage === 4 }" @click="TabPage = 4">喜歡的食物</button>
    </nav>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr "
      :class="{ 'bg-blue-500': TabPage === 2, 'bg-green-500': TabPage === 3, 'bg-yellow-400': TabPage === 4 }">
      <img :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2" v-if="TabPage === 1">
      <div v-else-if="TabPage === 2" class="text-[60px]">13</div>
      <div v-else-if="TabPage === 3" class="text-[60px]">楷鈞</div>
      <div v-else class="text-[40px]">金之園草袋飯</div>
    </div>
  </div>
</template>
<!-- 
    详细解释：

vueLogo：导入Vue的Logo图片，用于在页面上显示Vue的Logo。

TabPage：用于追踪当前显示的页面，初始值为1。

<nav>：导航栏，包含四个按钮，每个按钮对应一个页面。

<button>：每个按钮都有一个点击事件（@click="page = X"），点击时切换到相应的页面（1、2、3、4）。

<div>：内容区域，根据当前页面的不同应用不同的样式和显示内容。

:class="{ 'bg-red-400': page === 2, 'bg-blue-400': page === 3, 'bg-green-400': page === 4 }"：根据当前页面设置背景颜色。

根据 v-if、v-else-if 和 v-else 条件渲染不同的内容。

<style scoped>：使用了Scoped CSS，样式仅适用于当前组件。

.nav-btn：导航按钮的样式。

.active：被选中的按钮样式，有白色背景和黑色文字。
  -->

<style scoped>/* 都沒更動 style */
.nav-btn {
  @apply border-x-2 border-t-2 border-white rounded-t px-10 py-1 font-bold;
}

.active {
  @apply bg-white text-black;
}
</style>
