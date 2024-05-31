<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      id:0,
      btnArr:[
        {tag:'Vue',text:'實驗'},
        {tag:'編號',text:'26'},
        {tag:'姓名',text:'賴香吟'},
        {tag:'喜歡的食物',text:'蛋餅'},
      ]
    };
  },
  methods:{
    btnActive(index){
      this.id = index;
    }
  }
};
</script>

<template>
  <div class="w-[700px] h-[50dvh] font-NotoSans">
    <nav class="flex">
      <button 
        type="button"
        class="nav-btn"
        @click="btnActive(0)"
        :class="{'active': id === 0 }"
      >
        {{btnArr[0].tag}}
      </button>
      <button 
        type="button"
        class="nav-btn"
        @click="btnActive(1)"
        :class="{'active': id === 1 }"
      >
        {{btnArr[1].tag}}
      </button>
      <button 
        type="button"
        class="nav-btn"
        @click="btnActive(2)"
        :class="{'active': id === 2 }"
      >
        {{btnArr[2].tag}}
      </button>
      <button 
        type="button"
        class="nav-btn"
        @click="btnActive(3)"
        :class="{'active': id === 3 }"
      >
        {{btnArr[3].tag}}
      </button>
      
    </nav>
    <div 
      class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr" 
      :class="{'number':id === 1,'name':id === 2,'food':id === 3,}"
    >
      <img :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2" v-if="id === 0">
      <div class="text" v-else>{{btnArr[id].text}}</div>
    </div>

  </div>
</template>

<style scoped>
.nav-btn {
  @apply border-x-2 border-t-2 border-white rounded-t px-10 py-1 font-bold mr-1;
}
.active {
  @apply bg-white text-black;
}
.text{
  @apply font-RampartOne text-7xl text-black
}
.number{
  @apply  bg-rose-800
}
.name{
  @apply bg-cyan-800
}
.food{
  @apply bg-amber-800
}
</style>
