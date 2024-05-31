<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      // btn array
      btnArray: [],
      // bg-color
      // bgColor: ['bg-pink-600', 'bg-slate-600', 'bg-sky-400'],
      bgColor: 'none',
      show: false,
      activeItem:0,
    };
  },
  // function
  methods: {
    changeColor(e) {
      console.log(e);
    },
    setActive(index){
      this.activeItem = index;
    }
  }
};
</script>

<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <button type="button" class="nav-btn " @click="bgColor = 'none',setActive(0)" :class="{active: activeItem === 0}">Vue</button>
      <button type="button" class="nav-btn" @click="bgColor = 'bg-pink-600',setActive(1)" :class="{active: activeItem === 1}">編號</button>
      <button type="button" class="nav-btn" @click="bgColor = 'bg-slate-600',setActive(2)" :class="{active: activeItem === 2}">姓名</button>
      <button type="button" class="nav-btn" @click="bgColor = 'bg-sky-800',setActive(3)" :class="{active: activeItem === 3}">喜歡的食物</button>
    </nav>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr " :class="bgColor">
      <img :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2" v-if="bgColor == 'none'">
      <div class="text-5xl" v-if="bgColor == 'bg-pink-600'">20</div>
      <div class="text-5xl" v-if="bgColor == 'bg-slate-600'">洪季晴</div>
      <div class="text-5xl" v-if="bgColor == 'bg-sky-800'">火鍋</div>
    </div>
  </div>
</template>

<style scoped>
.nav-btn {
  @apply border-x-2 border-t-2 border-white rounded-t px-10 py-1 font-bold;
}

.active {
  @apply bg-white text-black ;
}
</style>
