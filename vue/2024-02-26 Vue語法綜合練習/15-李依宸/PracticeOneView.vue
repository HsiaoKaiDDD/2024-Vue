<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      currentTab: 'tab1',
      active:'bg-white text-black'
      
    };
  },
  methods:{
    setCurrentTab(tab){
      this.currentTab = tab;
    }
    
}
}
</script>

<template>
  <div class="w-[700px] h-[50dvh]">                      
    <nav class="flex">
      <button type="button" class="nav-btn" @click="setCurrentTab('tab1')" :class="{'active': currentTab === 'tab1'}" >Vue</button>
      <button type="button" class="nav-btn" @click="setCurrentTab('tab2')" :class="{'active': currentTab === 'tab2'}">編號</button>
      <button type="button" class="nav-btn" @click="setCurrentTab('tab3')" :class="{'active': currentTab === 'tab3'}">姓名</button>
      <button type="button" class="nav-btn" @click="setCurrentTab('tab4')" :class="{'active': currentTab === 'tab4'}">喜歡的食物</button>
    </nav>
    <div v-if="currentTab === 'tab1'"  class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr">
      <img :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2">
    </div>
    <div v-else-if="currentTab === 'tab2'" class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr bg-red-500">
      <div class="text-4xl">15</div>
    </div>
    <div v-else-if="currentTab === 'tab3'" class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr bg-blue-600">
      <div class="text-4xl">李依宸</div>
    </div>
    <div v-else class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr bg-green-400">
      <div class="text-4xl">珍奶</div>
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
