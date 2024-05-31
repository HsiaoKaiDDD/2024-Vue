<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      show: false,
      page: 1,
    };
  },
  methods: {
    addClass() {

    }
  }
};
</script>

<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <button type="button" class="nav-btn" :class="{ 'active': page === 1 }" @click="page = 1">Vue</button>
      <button type="button" class="nav-btn" :class="{ 'active': page === 2 }" @click="page = 2">編號</button>
      <button type="button" class="nav-btn" :class="{ 'active': page === 3 }" @click="page = 3">姓名</button>
      <button type="button" class="nav-btn" :class="{ 'active': page === 4 }" @click="page = 4">喜歡的食物</button>
    </nav>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr "
      :class="{ 'bg-red-400': page === 2, 'bg-blue-400': page === 3, 'bg-green-400': page === 4 }">
      <img :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2" v-if="page === 1">
      <div v-else-if="page === 2" class="text-[60px]">09</div>
      <div v-else-if="page === 3" class="text-[60px]">育先</div>
      <div v-else class="text-[60px]">壽司</div>
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
