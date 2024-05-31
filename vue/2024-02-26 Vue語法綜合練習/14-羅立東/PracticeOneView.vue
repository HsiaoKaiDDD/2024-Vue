<script>
import vueLogo from '@/assets/images/logo.svg';
import photoImg from '@/assets/images/9527.jpg';
import nameImg from '@/assets/images/華安.jpg';
import foodImg from '@/assets/images/紅燒翅.jpg';

export default {
  data() {
    return {
      photoImg,
      foodImg,
      nameImg,
      vueLogo,
      serialNumber: '',
      name: "",
      food: '',
      selectPage: 'vue', 
    };
  },
  methods: {
    setPage(page) {
      this.selectPage = page;
    },
  },
};
</script>

<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <button @click="setPage('vue')" :class="{ 'active': selectPage === 'vue' }" type="button" class="nav-btn">Vue</button>
      <button @click="setPage('number')" :class="{ 'active': selectPage === 'number' }" type="button" class="nav-btn">編號</button>
      <button @click="setPage('name')" :class="{ 'active': selectPage === 'name' }" type="button" class="nav-btn">姓名</button>
      <button @click="setPage('food')" :class="{ 'active': selectPage === 'food' }" type="button" class="nav-btn">喜歡的食物</button>
    </nav>
    <div v-if=" selectPage === 'vue'" class="flex items-center justify-center h-full border-2  rounded-b rounded-tr">
      <img :src="vueLogo" alt="Vue Logo" class="w-full h-full
      ">
    </div>
    <div v-if=" selectPage === 'number'" class="flex items-center justify-center h-full border-2  rounded-b rounded-tr">
      <img :src="photoImg" alt="photo" class="w-full h-full">
      {{ serialNumber }}
    </div>
    <div v-if=" selectPage === 'name'" class="flex items-center justify-center h-full border-2  rounded-b rounded-tr">
      <img :src="nameImg" alt="photo" class="w-full h-full">
      {{ name }}
    </div>
    <div v-if=" selectPage === 'food'" class="flex items-center justify-center h-full border-2  rounded-b rounded-tr">
      <img :src="foodImg" alt="photo" class="w-full h-full">
      {{ food }}
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
