<template>
    <div class="person">
        <h2>名称：{{name}}</h2>
        <h2>年龄：{{age}}</h2>
        <button @click="showTel">查看联系方式</button>
    </div>
</template>
<script lang="ts">
    export default {
        name:'Person',
    }
</script>
<script lang='ts' setup>//name='Person123'
    let name = '张三';
    let age = 18;
    let tel = '12345789'
    function showTel(){
        alert(tel)
    }
</script>
<style scoped>
    .person {
        background-color: pink;
        width: 800px;
        height: 200px;
    }
</style>