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
        beforeCreate() {
            console.log('beforeCreate');
        },
        setup(){
            console.log('执行时机比beforeCreate还提前');
            //setup函数中this是undefined
            let name = '张三';
            let age = 18;
            let tel = '12345789'
            function showTel(){
                alert(tel)
            }
            return {name,age,showTel} 
        },
    }
</script>
<style scoped>
    .person {
        background-color: pink;
        width: 800px;
        height: 200px;
    }
</style>