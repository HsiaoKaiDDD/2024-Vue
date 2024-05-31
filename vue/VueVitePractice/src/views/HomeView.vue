<script>
export default {
  data() {
    return {
      count: '2',
      className: 'text-4xl text-red-500',
      inputType: 'password',
      color: 'bg-blue-500',
      showPassword: false,
    };
  },
  methods: {
    addCount(){
      this.count++;
    },
    // 更換顏色
    changeColor() {
      this.color = this.color === 'bg-blue-500' ? 'bg-red-500' : 'bg-blue-500';
    },
    // 切換密碼顯示開關
    togglePassword() {
      // this.inputType = this.inputType === 'password' ? 'text' : 'password';
      this.showPassword = !this.showPassword; 
    },
  },
};
</script>

<template>
  <div class="flex flex-col gap-y-2">
    <h1 class="text-8xl font-bold">{{ count }}</h1>

    <!-- v-on 事件 -->
    <button type="button" v-on:click="count++">點我</button>
    <!-- methods -->
    <button type="button" @click="addCount()">click me</button>

    <!-- v-bind 控制所有屬性-->
    <div v-bind:class="className" class="text-black">ㄎwdwadwad</div>
    <input v-bind:type="inputType" class="text-black">
    <input :type="inputType" class="text-black">

    <!-- 練習 -->
    <button type="button" @click="changeColor" :class="color" class="w-10 h-10">
    {{ color === 'bg-blue-500' ? 'im blue' : 'im red' }}
    </button>

    <!-- 開關顯示密碼 -->
    <button type="button" @click="togglePassword">顯示/關閉密碼</button>
    <input :type="showPassword ? 'text' : 'password'" class="text-black">
    <button type="button" @click="togglePassword">顯示/關閉密碼</button>
  </div>
</template>

<style scoped>

</style>
