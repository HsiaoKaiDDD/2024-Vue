<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      blockNum: '1',
    };
  },
  methods: {
    toggleActive(num) {
      this.blockNum = num;
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
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr">
      <img v-show="blockNum === 1" :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2">
      <div v-show="blockNum === 2">73</div>
      <div v-show="blockNum === 3">兆凱</div>
      <div v-show="blockNum === 4">pizza</div>
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
