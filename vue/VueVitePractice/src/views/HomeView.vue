<script>
export default {
  data() {
    return {
      count: '2',
      className: 'text-4xl text-red-500',
      inputType: 'password',
      color: 'bg-blue-500',
      showPassword: false,
      nextTextValue: '',
      checkboxValue: '',
      singleCheckboxValue: '',
      multipleCheckboxValue: [],
      radioValue: '',
      fileData: null,
      show: false,
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
    getInputValue(e) {
      console.log(e.target.value);
    },
    getInputValues(e) {
      console.log(e);
    },

    // 上傳檔案
    uplaodFile(e) {
      if (e.target.files.length === 0){
        return;
      }
      const file = e.target.files[0];
      console.log(file.type)
      // 卡控 只包含圖片
      if (file.type.includes('image/')){
        // 生出圖片
        const img = URL.createObjectURL(file);
        this.fileData = img;
      }
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

    <label for="">
      文字輸入框
      <input type="text">
    </label>
    <!-- input event -->
    <input type="text" class="text-black" @input="(e) => getInputValue(e)">
    <!-- input change -->
    <input type="text" class="text-black" @change="getInputValues">

    <!-- v-model 雙向綁定 -->
    <input v-model="nextTextValue" type="text" class="text-black">
    {{ nextTextValue }}

    <input v-model="singleCheckboxValue" type="checkbox" :true-value="1" :false-value="0">
    {{ '單選:' + singleCheckboxValue }}
    <!-- 複選勾選欄 -->
    <input v-model="multipleCheckboxValue" type="checkbox" :value="1">
    <input v-model="multipleCheckboxValue" type="checkbox" :value="2">
    <input v-model="multipleCheckboxValue" type="checkbox" :value="3">
    {{ multipleCheckboxValue.toString() }}
    {{ multipleCheckboxValue.join('*') }}

    <div class="flex flex-col gap-y-2">
      <label>
        男
        <input v-model="radioValue" type="radio" value="boy">
      </label>
      <label>
        女
        <input v-model="radioValue" type="radio" value="girl">
      </label>
      <label>
        其他
        <input v-model="radioValue"  type="radio" value="other">
      </label>
      {{ radioValue }}
      <img :src="fileData" alt="">
    </div>

    <input type="file" accept=".jpg, .png, .gif" multiple @change="uplaodFile">

    <!-- V-SHOW -->
    <div v-show="show">出現</div>

    <!-- v-if -->
    <div v-if="show">appear</div>
    <div v-else>dissapear</div>
  </div>
</template>

<style scoped>

</style>
