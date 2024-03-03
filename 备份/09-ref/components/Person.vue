<template>
    <div class="person">
        <h2>汽车信息：一辆{{car.brand}}价值{{car.price}}万</h2>
        <button @click="show">修改</button>
        <br>
        <h2>游戏列表：</h2>
        <ul>
            <li v-for="g in games" :key="g.id">
            {{g.name}}</li>
        </ul>
        <button @click="show2">修改</button>
    </div>
</template>
<script lang='ts' setup name="Person">
    import {reactive,ref} from 'vue';
    //ref定义基本数据类型+对象数据类型，reactive只能定义对象数据类型
    //ref定义的对象类型，value值还是用reactive实现
    let car = ref({brand:'奔驰',price:100})
    let games = ref([
        {id:'11',name:'王者'},
        {id:'12',name:'王者2'},
        {id:'13',name:'王者3'},
    ])
    function show(){
        car.value.price += 10;
    }
    function show2(){
        games.value[0].name = '元神'
    }
</script>
<style scoped>
    .person {
        background-color: pink;
        width: 800px;
    }
</style>