<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      number: '25',
      name: '林佳汶',
      food: '拉麵',
      tab: '',
    };
  },

  methods: {
    //用分頁編號下去做控制
    tab1() {
      this.tab = '1';
    },
    tab2() {
      this.tab = '2';
    },
    tab3() {
      this.tab = '3';
    },
    tab4() {
      this.tab = '4';
    },
  },
};
</script>

<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <!-- 按下去後觸發fn tab1，讓狀態改為active且tab編號為1 -->
      <button type="button" class="nav-btn" @click="tab1" :class="{ 'active': tab === '1' }">Vue</button>
      <button type="button" class="nav-btn" @click="tab2" :class="{ 'active': tab === '2' }">編號</button>
      <button type="button" class="nav-btn" @click="tab3" :class="{ 'active': tab === '3' }">姓名</button>
      <button type="button" class="nav-btn" @click="tab4" :class="{ 'active': tab === '4' }">喜歡的食物</button>
    </nav>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr">
      <!-- v-if顯示狀態 -->
      <img :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2" v-if="tab === '1'">
      <div
        class="text-3xl flex items-center justify-center border-2 border-white rounded-b rounded-tr bg-blue-300 w-full h-full"
        v-if="tab === '2'"> {{ number
        }}</div>
      <div
        class="text-3xl flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr bg-green-600 w-full h-full"
        v-if="tab === '3'">
        {{ name
        }}</div>
      <div
        class="text-3xl flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr bg-gray-600 w-full h-full"
        v-if="tab === '4'">
        {{ food
        }}</div>
    </div>
  </div>
</template>

<style scoped>
.nav-btn {
  @apply border-x-2 border-t-2 border-white rounded-t px-10 py-1 font-bold;
}

.active {
  @apply bg-white text-black;
}</style>
