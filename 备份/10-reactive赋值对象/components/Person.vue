<template>
    <div class="person">
        <h2>汽车信息：一辆{{car.brand}}价值{{car.price}}万</h2>
        <button @click="show">修改整个对象</button>
        <h2>求和数:{{sum}}</h2>
        <button @click="sumShow">每次加10</button>
    </div>
</template>
<script lang='ts' setup name="Person">
    import {reactive,ref} from 'vue';
    //有插件自动补齐.value
    //reactive有缺点，若要替换整个对象，用Object.assign整体替换
    //rractive重新分配对象，会失去响应式
    //ref重新分配对象可以直接赋值，因为ref的.value操作，一定是响应式对象
    let car = reactive({brand:'奔驰',price:100})
    let sum = ref(0)
    function show(){
        //把b参数赋值给a参数，会覆盖，a地址不变
        Object.assign(car,{brand:'宝马',price:90})
    }
    function sumShow(){
        sum.value += 10
    }
    /**
     * 使用原则：
     * 需要基本类型的响应式数据，用ref
     * 需要响应式对象，层级不深，ref和reactive都可
     * 需要响应式对象，层级较深，用reactive
     */
</script>
<style scoped>
    .person {
        background-color: pink;
        width: 800px;
    }
</style>