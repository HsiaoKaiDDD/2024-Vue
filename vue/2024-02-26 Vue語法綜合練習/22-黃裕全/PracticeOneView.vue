<script>
// (import引入)(form是從哪邊引入)(@/ => 會指到src身上)
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      // (左邊為key):(右邊為value)
      // (物件的key)跟(物件的value)是一樣的話，value可以做省略
      vueLogo,//等同於vueLogo: vueLogo,
      selectedTab: 'logo',
      msg: '',
      // color: '',
    };
  },
  methods:{
    // 切換頁籤
    // 再傳一個參數msg，【msg = ''，這段話就是假設預設值msg誤傳的時候就是空字串】
    changeTab(tab, msg = '') {
      this.selectedTab = tab;
      this.msg = msg;
      // this.color = color;//辰洧寫法
    },
    // 回傳指定背景顏色class
    bgColoe() {
      if (this.selectedTab === 'number') {
        return 'bg-red-500';
      }
      if (this.selectedTab === 'name') {
        return 'bg-blue-500';
      }
      // 然後function可以一直加下去，然後v-bind綁定去找每個:class="bgColoe()"的fucntion
      if (this.selectedTab === 'food') {
        return 'bg-violet-500';
      }
      // return一定會去字串結果，要嘛是空
      return '';
    },
  }
}
</script>

<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <!-- logo可以不用傳嘛，因為我們選到圖片的時候不需要顯自文字，所以可以不用傳msg  -->
      <button type="button" class="nav-btn" :class="{active : selectedTab === 'logo'}" @click="changeTab('logo')">Vue</button>
      <button type="button" class="nav-btn" :class="{active : selectedTab === 'number'}" @click="changeTab('number', '23')">編號</button>
      <button type="button" class="nav-btn" :class="{active : selectedTab === 'name'}" @click="changeTab('name', 'simom')">姓名</button>
      <button type="button" class="nav-btn" :class="{active : selectedTab === 'food'}" @click="changeTab('food', '珍珠奶茶')">喜歡的食物</button>
    </nav>
    <!-- 把辰洧的拿掉color暫時拿掉，使用老師方法 -->
    <div class="flex items-center justify-center h-full border-2  border-white rounded-b rounded-tr" :class="bgColoe()">
      <img v-if="selectedTab === 'logo'" :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2">
      <!-- <div v-if="selectedTab === 'number'" class="text-7xl">23</div>
      <div v-if="selectedTab === 'name'" class="text-7xl">simom</div>
      <div v-if="selectedTab === 'food'" class="text-7xl">火鍋</div> -->
      <div class="text-7xl">{{ msg }}</div>
    </div>
  </div>
</template>
<style scoped>
.nav-btn{
  @apply border-x-2 border-t-2 border-white rounded-t px-10 py-1 font-bold;
}

.active {
  @apply bg-white text-black;
}
/* #red {
  background-color: red;
}
#green {
  background-color: green;
}
#violet {
  background-color: violet;
} */
</style>
看到31分13秒