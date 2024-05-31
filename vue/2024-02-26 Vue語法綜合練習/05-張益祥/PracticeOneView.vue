<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      page: '1',
      number: '5',
      name:'張益祥',
      sukifood: '咖哩',

    };
  },
  methods: {

    page1() {
      this.page = '1';

    },
    page2() {
      this.page = '2';
    },
    page3() {
      this.page = '3';
    },
    page4() {
      this.page = '4';
    },

    
  }
};
</script>

<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <button type="button" class="nav-btn" @click="page1" :class="{'active': page === '1' }"> Vue </button>
      <button type="button" class="nav-btn" @click="page2" :class="{'active': page === '2' }"> 編號 </button>
      <button type="button" class="nav-btn" @click="page3" :class="{'active': page === '3' }"> 姓名 </button>
      <button type="button" class="nav-btn" @click="page4" :class="{'active': page === '4' }"> 喜歡的食物 </button>
    </nav>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr">
      <img :src="vueLogo" v-if="page === '1'" alt="Vue Logo"  class="w-1/2 h-1/2">
      <div v-if="page === '2'" class="w-full h-full bg-teal-950 text-center leading-[50dvh] text-9xl"> {{ number }}
      </div>
      <div v-if="page === '3'" class="w-full h-full bg-teal-700 text-center leading-[50dvh] text-5xl"> {{ name }}
      </div>
      <div v-if="page === '4'" class="w-full h-full bg-teal-500 text-center leading-[50dvh] text-5xl "> {{ sukifood }}
      </div>
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
