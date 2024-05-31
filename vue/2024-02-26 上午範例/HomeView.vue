<script>
export default {
  // 放變數的地方
  data() {
    return {
      name: 'Stanley',
      count: 1,
      className: 'red text-green-500 text-3xl',
      inputType: 'text',
      textValue: '',
      color: 'bg-blue-500',
      password: 'password',
      showPassword: false,
      newTextValue: '',
    };
  },
  // 放函式的地方
  methods: {
    // 增加數字
    addCount() {
      this.count++;
    },
    // 更換顏色
    changeColor() {
      console.log(this.color);
      this.color = 'bg-red-500';
      console.log(this.color);
    },
    // 切換顯示密碼
    changeDisplay() {
      this.showPassword = !this.showPassword;
      // if (this.password === 'password') {
      //   this.password = 'text';
      // } else {
      //   this.password = 'password';
      // }
    },
    // 獲取Input的值
    getInputValue(e) {
      console.log(e.target.value);
      this.textValue = e.target.value;
    },
  },
};
</script>

<template>
  <div class="flex flex-col gap-y-2">
    <!-- 模板變數 -->
    <h2>模板變數</h2>
    <h1 class="text-5xl font-bold">{{ name }}</h1>
    <h2 class="text-5xl font-bold">計數：{{ count }}</h2>

    <!-- v-on 事件 -->
    <br>
    <h2>v-on 事件</h2>
    <button type="button" class="border border-white" v-on:click="count++">
      請按我增加數字
    </button>
    <button type="button" class="border border-white" @click="addCount()">
      請按我增加數字
    </button>
    <input type="text" class="text-black" @input="(e) => getInputValue(e)">
    <!-- <input type="text" class="text-black" @input="getInputValue"> -->
    <div>{{ textValue }}</div>

    <!-- v-bind 屬性綁定 -->
    <br>
    <h2>v-bind 屬性綁定</h2>
    <div v-bind:class="className">Class綁定</div>
    <input v-bind:type="inputType" class="text-black">
    <input :type="inputType" class="text-black">

    <!-- 課堂綜合練習1 -->
    <br>
    <h2>課堂綜合練習1</h2>
    <button type="button" class="border border-white" @click="changeColor()">
      按我變紅色
    </button>
    <div class="w-[100px] h-[100px] text-2xl" :class="color">
      {{ color === 'bg-blue-500' ? '我原本是藍色' : '我現在是紅色' }}
    </div>

    <!-- 課堂綜合練習2 -->
    <br>
    <h2>課堂綜合練習2</h2>
    <button type="button" class="border border-white" @click="changeDisplay()">
      顯示/關閉密碼
    </button>
    <input :type="showPassword ? 'text' : 'password'" class="text-black">

    <!-- v-model 雙向綁定 -->
    <br>
    <h2>v-model 雙向綁定</h2>
    <input v-model="newTextValue" type="text" class="text-black">
    {{ newTextValue }}
  </div>
</template>

<style scoped>
.red {
  text-align: center;
  background-color: red;
}
</style>
