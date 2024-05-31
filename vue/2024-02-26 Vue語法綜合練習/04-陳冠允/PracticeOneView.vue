<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      activeBtn: 'vue',
    };
  },
  methods: {},
};
</script>
<object data="" type=""></object>
<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <button type="button" class="nav-btn" :class="{ active: activeBtn == 'vue' }" @click="activeBtn = 'vue'">Vue</button>
      <button type="button" class="nav-btn" :class="{ active: activeBtn == 'id' }" @click="activeBtn = 'id'">id</button>
      <button type="button" class="nav-btn" :class="{ active: activeBtn == 'name' }" @click="activeBtn = 'name'">name</button>
      <button type="button" class="nav-btn" :class="{ active: activeBtn == 'food' }" @click="activeBtn = 'food'">food</button>
    </nav>
    <div class="borders" v-show="activeBtn == 'vue'">
      <img :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2" />
    </div>
    <div class="borders bg-slate-300" v-show="activeBtn == 'id'">04</div>
    <div class="borders bg-red-300" v-show="activeBtn == 'name'">陳冠允</div>
    <div class="borders bg-blue-300" v-show="activeBtn == 'food'">吃的</div>
  </div>
</template>

<style scoped>
.nav-btn {
  @apply border-x-2 border-t-2 border-white rounded-t px-10 py-1 font-bold;
}

.active {
  @apply bg-white text-black;
}
.borders {
  @apply flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr;
}
</style>
