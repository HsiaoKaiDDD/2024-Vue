<script>
export default {
  data() {
    return {
      count: '2',
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
      className: 'bg-red-500',
      arr: [1, 2, 3],
      myObj: {
        id: 1,
        name: 'eric',
      },
      practiceObj: 
      [
        {
          id: 1,
          name: 'eric',
          identityC: 'B12233232',
          gender: 'man',
          phone: '0905411895',
        },
        {
          id: 2,
          name: 'eric',
          identityC: 'B12233232',
          gender: 'man',
          phone: '0905411895',
        },
        {
          id: 3,
          name: 'eric',
          identityC: 'B12233232',
          gender: 'women',
          phone: '0905411895',
        },
        {
          id: 4,
          name: 'eric',
          identityC: 'B12233232',
          gender: 'women',
          phone: '0905411895',
        },
      ],
      selectTab: '',
    };
  },
  computed: {
    filterData() {
      if(!this.selectTab) {
        return this.practiceObj;
      }
      return this.practiceObj.filter(user => user.gender === this.selectTab);
    },
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
    // 添加陣列
    addArr() {
      // 找出陣列最後一個
      // 方法1
      // const lastItem = this.arr[this.arr.length - 1];
      // 方法2
      const lastItem = this.arr.at(-1) ?? 0;
      console.log(this.arr.length);
      this.arr.push(lastItem + 1);
    },
    deleteArr() {
      this.arr.splice(-1, 1);
    },
    // 刪除陣列
    deleteItem(id) {
      const targetId = id;
      console.log(targetId)
      this.practiceObj.splice(targetId, 1);
    },
    // 更換篩選
    changeTab(target) {
      this.selectTab = target;
    }
  },
};
</script>

<template>
  <div class="flex flex-col gap-y-2 py-[50px]">
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

    <!-- v-bind -->
    <div class="w-[100px] h-[100px]" :class="show ? 'bg-red-500' : 'bg-blue-500'"></div>
    <div class="w-[100px] h-[100px] bg-red-500" :class="{ 'text-yellow-500' : show ,'text-5xl' :rule === 'if' }">23</div>

    <!-- v-for -->
    <div v-for="(item, index) in arr" :key="index">
      {{ index }} : {{ item }}
    </div>

    <!-- 練習:打印1-99 -->
    <!-- <div v-for="(item , index) in 99" :key="index">
      {{ item }}
    </div> -->

    <!-- 打印object -->
    <div v-for="(value, key , index) in myObj" :key="index">
      {{ key }} {{ value }}
    </div>

    <!-- 練習 -->
    <button type="button" @click="addArr">新增</button>
    <button type="button" @click="deleteArr">刪除</button>
    {{ arr }}

    <!-- 練習 -->
    <nav>
      <button type="button" @click="changeTab('')">不限</button>
      <button type="button" @click="changeTab('man')">篩選男</button>
      <button type="button" @click="changeTab('women')">篩選女</button>
    </nav>
    <table>
      <tr>
        <th>編號</th>
        <th>姓名</th>
        <th>身分證字號</th>
        <th>性別</th>
        <th>電話</th>
        <th>功能</th>
      </tr>
      <tbody v-for="(value, key , index) in filterData" :key="index">
        <td>{{ value.id }}</td>
        <td>{{ value.name }}</td>
        <td>{{ value.identityC }}</td>
        <td>{{ value.gender === 'man' ? '男' : '女' }}</td>
        <td>{{ value.phone }}</td>
        <td>
          <button type="button" @click="deleteItem(key)">刪除</button>
        </td>
      </tbody>
    </table>
  </div>
</template>

<style scoped>

</style>
