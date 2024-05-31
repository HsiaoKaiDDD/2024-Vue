<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      page:'1',
    };
  },

methods: {
  number() {
    this.page = '2'
  },
  name() {
  this.page = '3'
  },
  food() {
  this.page = '4'
  },
  vue(){
    this.page = '1'
  }
 },
};

</script>

<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <button type="button" class="nav-btn" :class="{'active':page === '1'}" @click="vue()">Vue</button>
      <button type="button" class="nav-btn" :class="{'active':page === '2'}" @click="number()">編號</button>
      <button type="button" class="nav-btn" :class="{'active':page === '3'}" @click="name()">姓名</button>
      <button type="button" class="nav-btn" :class="{'active':page === '4'}" @click="food()">喜歡的食物</button>
    </nav>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr" v-if="page === '1'">
      <img :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2">
    </div>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr bg-red-300 text-black text-8xl" v-if="page === '2'">2
    </div>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr bg-zinc-400  text-black text-8xl" v-if="page === '3'">馮琮凱
    </div>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr bg-blue-300  text-black text-8xl" v-if="page ==='4'">燒肉
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