<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      background:1,
    };
    
  },
  methods:{
    changeColor(e){
      // let e=this.background; 會失敗
      this.background=e;
      console.log(this.background);
    },
  },
};
</script>

<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <button type="button" class="nav-btn " @click="changeColor(1)" :class="background===1 ? 'bg-white text-black':'bg-black text-white'">Vue</button>
      <button type="button" class="nav-btn" @click="changeColor(2)" :class="background===2 ? 'bg-white text-black':'bg-black text-white'">編號</button>

      <button type="button" class="nav-btn" @click="changeColor(3)" :class="background===3 ? 'bg-white text-black':'bg-black text-white'">姓名</button>
      <button type="button" class="nav-btn" @click="changeColor(4)" :class="background===4 ? 'bg-white text-black':'bg-black text-white'">喜歡的食物</button>
    </nav>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr">
      <img v-if="background===1" :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2">
      <div v-else-if="background===2" >18</div>
      <div v-else-if="background===3" >陳宥嫣</div>
      <div v-else >好吃ㄉ食物</div>
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
