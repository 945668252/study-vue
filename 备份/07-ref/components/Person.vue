<template>
    <div class="person">
        <h2>名称：{{name}}</h2>
        <h2>年龄：{{age}}</h2>
        <button @click="showTel">查看联系方式</button>
        <button @click="editName">修改名称</button>
        <button @click="editAge">修改年龄</button>
    </div>
</template>
<script lang="ts">
    export default {
        name:'Person',
    }
</script>
<script lang='ts' setup>
    import {ref} from 'vue';
    //ref模板中不用value，ts中需要用value
    let name = ref('张三');
    let age = ref(18);
    let tel = '12345789'
    function showTel(){
        alert(tel)
    }
    function editName(){
        name.value = 'GG'
    }
    function editAge(){
        age.value++;
    }
</script>
<style scoped>
    .person {
        background-color: pink;
        width: 800px;
        height: 200px;
    }
</style>