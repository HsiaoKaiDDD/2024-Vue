<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      rule:'0'
    };
  },
  methods:{
    change0(){
      this.rule = '0';
    },
    change1(){
      this.rule = '1';
    },
    change2(){
      this.rule = '2';
    },
    change3(){
      this.rule = '3';
    },
  },
};
</script>

<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <button type="button" @click="change0()" class="nav-btn" :class="{'active':rule === '0'}" >Vue</button>
      <button type="button" @click="change1()" class="nav-btn" :class="{'active':rule === '1'}" >編號</button>
      <button type="button" @click="change2()" class="nav-btn" :class="{'active':rule === '2'}" >姓名</button>
      <button type="button" @click="change3()" class="nav-btn" :class="{'active':rule === '3'}" >喜歡的食物</button>
    </nav>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr">
      <img :src="vueLogo" alt="Vue Logo" :class="{'w-1/2 h-1/2':rule === '0'}" v-if="rule === '0'">
      <div :class="{'w-full h-full bg-red-500 text-9xl flex justify-center items-center':rule === '1'}" v-if="rule === '1'">17</div>
      <div :class="{'w-full h-full bg-green-500 text-9xl flex justify-center items-center':rule === '2'}" v-if="rule === '2'">林子超</div>
      <div :class="{'w-full h-full bg-yellow-500 text-9xl flex justify-center items-center':rule === '3'}" v-if="rule === '3'">火鍋</div>
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
