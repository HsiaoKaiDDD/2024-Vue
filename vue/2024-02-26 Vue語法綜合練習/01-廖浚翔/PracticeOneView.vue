<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      selectedTab: 'logo',
      msg: '',
    };
  },
  methods: {
    changeTab(tab, msg ='') {
      this.selectedTab = tab;
      this.msg = msg;
    },

    //回傳指定背景顏色
    bgColor() {
      if (this.selectedTab === 'number') {
        return 'bg-red-500';
      }
      if (this.selectedTab === 'name') {
        return 'bg-blue-500';
      }
      if (this.selectedTab === 'food') {
        return 'bg-green-500';
      }
      return '';
    }

  },
};
</script>

<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <button type="button" class="nav-btn" :class="{ 'active':selectedTab === 'logo' }" @click="changeTab('logo')">Vue</button>
      <button type="button" class="nav-btn" :class="{ 'active':selectedTab === 'number'}" @click="changeTab('number','1')">編號</button>
      <button type="button" class="nav-btn" :class="{ 'active':selectedTab === 'name' }" @click="changeTab('name','Ryan')">姓名</button>
      <button type="button" class="nav-btn" :class="{ 'active':selectedTab === 'food' }" @click="changeTab('food','西瓜')">喜歡的食物</button>
    </nav>
    <div :class="bgColor()" class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr">
      <img v-if="selectedTab ==='logo'" :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2">
      <!--<div v-if="selectedTab ==='number'" class="text-7xl">1</div>
      <div v-if="selectedTab ==='name'" class="text-7xl">名</div>
      <div v-if="selectedTab ==='food'" class="text-7xl">西瓜</div> -->
      <div class="text-7xl" @click="bgColor()">{{ msg }}</div>
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
