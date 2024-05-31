<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
  data() {
    return {
      vueLogo,
      number: '',
      name: '',
      likeFood: '',
      color: 'black',
      changeClass: 'w-1/2 h-1/2'
    };
  },
  methods: {
  changeColor(newColor) {
    this.color = newColor;
    if (newColor !== 'black') {
      this.changeClass = 'hidden';
    } else {
      this.changeClass = 'w-1/2 h-1/2';
    }
  },
},
}

</script>

<template>
  <div class="w-[700px] h-[50dvh]">
    <nav class="flex">
      <button type="button" class="nav-btn" :class="{ 'active': color === 'black' }" @click="changeColor('black')">Vue</button>
      <button type="button" class="nav-btn" :class="{ 'active': color === 'red' }" @click="changeColor('red')">編號</button>
      <button type="button" class="nav-btn" :class="{ 'active': color === 'blue' }" @click="changeColor('blue')">姓名</button>
      <button type="button" class="nav-btn" :class="{ 'active': color === 'green' }" @click="changeColor('green')">喜歡的食物</button>
    </nav>
    <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr" :id="color">
      {{ color === 'blue' ? 'kirito' : ''}}
      {{ color === 'red' ? '01' : ''}}
      {{ color === 'green' ? '壽司' :  ''}}
      <img :src="vueLogo" alt="Vue Logo" :class="changeClass">
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
#red {
  background-color: red;
  font-size: 50px;
}
#blue {
  background-color: blue;
  font-size: 50px;
}
#green {
  background-color: green;
  font-size: 50px;
}
.hidden {
  display: none;
}
</style>
