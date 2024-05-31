<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      number:'12',
      name:'趙建泓',
      food:'燒肉',
      activeTab: 'logo',
    };
  },

};
</script>

<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <button type="button" class="nav-btn" @click="activeTab = 'logo'" :class="{ 'active': activeTab === 'logo' }">Vue</button>
      <button type="button" class="nav-btn" @click="activeTab = 'number'" :class="{ 'active': activeTab === 'number' }">編號</button>
      <button type="button" class="nav-btn" @click="activeTab = 'name'" :class="{ 'active': activeTab === 'name' }">姓名</button>
      <button type="button" class="nav-btn" @click="activeTab = 'food'" :class="{ 'active': activeTab === 'food' }">喜歡的食物</button>
    </nav>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr">
      <img v-if="activeTab === 'logo'" :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2" >
      <div v-if="activeTab === 'number'" class="content bg-slate-400" >{{ number }}</div>
      <div v-if="activeTab === 'name'" class="content bg-red-500">{{ name }}</div>
      <div v-if="activeTab === 'food'" class="content bg-purple-600">{{ food }}</div>
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
.content{
  @apply w-full h-full flex justify-center items-center text-5xl;
}
</style>
