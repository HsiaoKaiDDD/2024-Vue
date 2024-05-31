<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      show:'vue',
    };
  },
  methods:{
    
  },
};
</script>

<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <button type="button" class="nav-btn" :class="{'active': show == 'vue'}" @click="show = 'vue'">Vue</button>
      <button type="button" class="nav-btn" :class="{'active': show == 'number'}" @click="show = 'number'">編號</button>
      <button type="button" class="nav-btn" :class="{'active': show == 'name'}" @click="show = 'name'">姓名</button>
      <button type="button" class="nav-btn" :class="{'active': show == 'food'}" @click="show = 'food'">喜歡的食物</button>
    </nav>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr" v-if="show === 'vue'">
      <img :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2">
    </div>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr text-9xl bg-blue-500" v-if="show === 'number'">
      10
    </div>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr text-9xl bg-gray-500" v-if="show === 'name'">
      王奕儒
    </div>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr text-9xl bg-green-500" v-if="show === 'food'">
      拉麵
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
