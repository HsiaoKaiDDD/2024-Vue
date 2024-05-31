<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      selectedContent: 'vue', // 默認選中 Vue 页面
      colorMap: {  // 每個頁面對應的背景色
        'vue': 'bg-blue-500',
        'id': 'bg-red-500',
        'name': 'bg-green-500',
        'food': 'bg-yellow-500'
      },
      color: 'bg-blue-500', // 初始背景色，默認 Vue 頁面的背景色
    };
  },
  methods: {
    // 切換頁面，並更新背景色
    selectContent(content) {
      this.selectedContent = content;
      this.color = this.colorMap[content];
    },
  },
};
</script>

<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <!-- 绑定點擊事件，切換選中的頁面 -->
      <button type="button" class="nav-btn" :class="{ 'active': selectedContent === 'vue' }" @click="selectContent('vue')">Vue</button>
      <button type="button" class="nav-btn" :class="{ 'active': selectedContent === 'id' }" @click="selectContent('id')">編號</button>
      <button type="button" class="nav-btn" :class="{ 'active': selectedContent === 'name' }" @click="selectContent('name')">姓名</button>
      <button type="button" class="nav-btn" :class="{ 'active': selectedContent === 'food' }" @click="selectContent('food')">喜歡的食物</button>
    </nav>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr" :class="color">

      <!-- 頁面的内容 -->
      <template v-if="selectedContent === 'vue'">
        <img :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2">
      </template>
      <template v-else-if="selectedContent === 'id'">
        <p>24</p>
      </template>
      <template v-else-if="selectedContent === 'name'">
        <p>吳詒珊</p>
      </template>
      <template v-else-if="selectedContent === 'food'">
        <p>燒肉</p>
      </template>
    </div>
  </div>
</template>

<style scoped>
.nav-btn {
  @apply border-x-2 border-t-2 border-white rounded-t px-10 py-1 font-bold;
}

.active {
  @apply bg-white text-black;
}
</style>
