<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,

      bgColor: '',
      textColor: '',

      bgColor2: '',
      textColor2: '',

      bgColor3: '',
      textColor3: '',

      bgColor4: '',
      textColor4: '',

      picture:'',
      
      box:'hidden',

      box2:'hidden',

      box3:'hidden',

    };
  },

  methods: {
    chageBgColor() {
      this.bgColor = 'bg-white';
      this.textColor = 'text-black';

      this.bgColor2 = '';
      this.textColor2 = '';

      this.bgColor3 = '';
      this.textColor3 = '';

      this.bgColor4 = '';
      this.textColor4 = '';

      this.picture = '';

      this.box ='hidden';

      this.box2 ='hidden';

      this.box3 ='hidden';

    },

    chageBgColor2() {
      this.bgColor2 = 'bg-white';
      this.textColor2 = 'text-black';

      this.bgColor = '';
      this.textColor = '';

      this.bgColor3 = '';
      this.textColor3 = '';

      this.bgColor4 = '';
      this.textColor4 = '';
      
      this.picture='hidden';
      
      this.box='block';

      this.box2 ='hidden';

      this.box3 ='hidden';      
    },

    chageBgColor3() {
      this.bgColor3 = 'bg-white';
      this.textColor3 = 'text-black';

      this.bgColor = '';
      this.textColor = '';

      this.bgColor2 = '';
      this.textColor2 = '';

      this.bgColor4 = '';
      this.textColor4 = '';

      this.picture='hidden';
      
      this.box='hidden';

      this.box2 ='block';

      this.box3 ='hidden';      
    },

    chageBgColor4() {
      this.bgColor4 = 'bg-white';
      this.textColor4 = 'text-black';

      this.bgColor = '';
      this.textColor = '';

      this.bgColor2 = '';
      this.textColor2 = '';

      this.bgColor3 = '';
      this.textColor3 = '';

      this.picture='hidden';
      
      this.box='hidden';

      this.box2 ='hidden';

      this.box3 ='block';      
    },

  }
};
</script>

<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <button type="button" class="nav-btn" :class="bgColor, textColor" @click="chageBgColor()">Vue</button>
      <button type="button" class="nav-btn" :class="bgColor2, textColor2" @click="chageBgColor2()">編號</button>
      <button type="button" class="nav-btn" :class="bgColor3, textColor3" @click="chageBgColor3()">姓名</button>
      <button type="button" class="nav-btn" :class="bgColor4, textColor4" @click="chageBgColor4()">喜歡的食物</button>
    </nav>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr">
      <img :src="vueLogo" alt="Vue Logo" class=" w-1/2 h-1/2 " :class="picture" @click="chageBgColor()">
      <div class="w-full h-full bg-red-500 text-center text-9xl  flex flex-col justify-center" :class="box" @click="chageBgColor2()">17</div>

      <div class="w-full h-full bg-green-500 text-center text-9xl  flex flex-col justify-center" :class="box2" @click="chageBgColor2()">林子超</div>

      <div class="w-full h-full bg-yellow-500 text-center text-9xl  flex flex-col justify-center" :class="box3" @click="chageBgColor2()">火鍋</div>
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
