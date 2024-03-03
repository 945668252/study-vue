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
        data(){
            return {
                name:'张三',
                age:17,
                tel:'123456789',
            }
        },
        methods:{
            showTel(){
                alert(this.tel);
            },
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