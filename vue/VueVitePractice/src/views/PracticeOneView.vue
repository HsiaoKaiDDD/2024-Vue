<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      blockNum: 1,
    };
  },
  methods: {
    toggleActive(num) {
      this.blockNum = num;
    },
  },
  computed: {
    bgColor() {
      if (this.blockNum === 1) {
        return 'bg-red-500';
      }
      if (this.blockNum === 2) {
        return 'bg-blue-500';
      }
      if (this.blockNum === 3) {
        return 'bg-yellow-500';
      }
      if (this.blockNum === 4) {
        return 'bg-gray-500';
      }
      return '';
    },
    changeMsg() {
      if (this.blockNum === 1) {
        return '';
      }
      if (this.blockNum === 2) {
        return '0';
      }
      if (this.blockNum === 3) {
        return 'eric';
      }
      if (this.blockNum === 4) {
        return 'pizza';
      }
      return '';
    },
  },
};
</script>

<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <button type="button" class="nav-btn" :class="{ 'active': blockNum === 1 }" @click="toggleActive(1)">Vue</button>
      <button type="button" class="nav-btn" :class="{ 'active': blockNum === 2 }" @click="toggleActive(2)">編號</button>
      <button type="button" class="nav-btn" :class="{ 'active': blockNum === 3 }" @click="toggleActive(3)">姓名</button>
      <button type="button" class="nav-btn" :class="{ 'active': blockNum === 4 }" @click="toggleActive(4)">喜歡的食物</button>
    </nav>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr" :class="bgColor">
      <img v-show="blockNum === 1" :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2">
      <div>{{ changeMsg }}</div>
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
