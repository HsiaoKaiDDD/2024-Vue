<script>
import vueLogo from '@/assets/images/logo.svg';

export default {
    data() {
        return {
            vueLogo,
            currentTab: 'Vue',
        };
    },
};
</script>

<template>
    <div class="w-[700px] h-[50dvh]">
        <nav class="flex">
            <button type="button" class="nav-btn" :class="{ active: currentTab === 'Vue' }"
                @click="currentTab = 'Vue'">Vue</button>
            <button type="button" class="nav-btn" :class="{ active: currentTab === '編號' }"
                @click="currentTab = '編號'">編號</button>
            <button type="button" class="nav-btn" :class="{ active: currentTab === '姓名' }"
                @click="currentTab = '姓名'">姓名</button>
            <button type="button" class="nav-btn" :class="{ active: currentTab === '喜歡的食物' }"
                @click="currentTab = '喜歡的食物'">喜歡的食物</button>
        </nav>

        <div class="flex items-center justify-center h-full border-2 border-white rounded-b rounded-tr">
            <template v-if="currentTab === 'Vue'">
                <img :src="vueLogo" alt="Vue Logo" class="w-1/2 h-1/2">
            </template>
            <template v-else-if="currentTab === '編號'">
                <p class="number">3</p>
            </template>
            <template v-else-if="currentTab === '姓名'">
                <p class="name">Xin</p>
            </template>
            <template v-else>
                <img src="../assets/images/統一布丁.jpg" alt="布丁" class="food">
            </template>
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

.food{
  width: 350px;
  height: 350px;
}

.name{
    padding: 130px;
    text-align: center;
    font-weight: bold;
    font-size: 132px;
    background-color: rgb(35, 35, 172);
    width: 90%;
    height: 90%;
    color: #6279ff;
}

.number{
    padding: 130px;
    text-align: center;
    font-weight: bold;
    font-size: 132px;
    background-color: rgb(136, 172, 35);
    width: 90%;
    height: 90%;
}
</style>
