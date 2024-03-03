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
        setup(){
            //V2可以V3数据，用this使用，因为setup比beforecreate先执行完毕
            //v3不可从v2读数据
            let name = '张三';
            let age = 18;
            let tel = '12345789'
            function showTel(){
                alert(tel)
            }
            return {name,age,showTel} 

            // return ()=>'哈哈'//可直接返回函数，类似react
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