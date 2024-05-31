<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      number:23,
      showClass:0,
      name:'楊景宏',
      likeFood:'炸物',
      className:'',
    };
  },
  methods:{
    showVue(){
      this.showClass = 0;
      this.className = '';
    },
    showNumber(){
      this.showClass = 1;
      this.className = 'bg-red-500';
    },
    showName(){
      this.showClass = 2;
      this.className = 'bg-stone-500';
    },
    showFood(){
      this.showClass = 3;
      this.className = 'bg-yellow-500';
    }
  },
};
</script>

<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <button type="button" class="nav-btn " @click="showVue()"
      :class="showClass ? '' :'active'">Vue</button>
      <button type="button" class="nav-btn" @click="showNumber()" :class="showClass == 1 ? 'active' :''">編號</button>
      <button type="button" class="nav-btn" @click="showName()" :class="showClass == 2 ? 'active' :''">姓名</button>
      <button type="button" class="nav-btn" @click="showFood()" :class="showClass == 3 ? 'active' :''">喜歡的食物</button>
    </nav>
    <div class=" flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr"
    :class="className">
      <img :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2" v-if = "showClass === 0">
      <div v-else-if = "showClass === 1" class="text-5xl">{{ number }}</div>
      <div v-else-if = "showClass === 2" class="text-5xl">{{ name }}</div>
      <div v-else class="text-5xl">{{ likeFood }}</div>

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
