<template>
    <div class="person">
        <h2>学生信息</h2>
        <h2>名称：{{name}}</h2>
        <h2>年龄：{{age}}</h2>
        <h2>测试：{{n1}}</h2>
        <button @click="show">修改名称</button>
        <button @click="show2">修改年龄</button>
    </div>
</template>
<script lang='ts' setup name="Person">
    import {reactive,toRefs,toRef} from 'vue';
    /**
     * toRefs把reactive定义的对象所有属性，改为ref定义的对象，且两个属性地址相同
     * 所以person.name和name的值一样
     * toRef需要把每个属性都取一遍
     */
    let person = reactive({name:'张三',age:18})
    // let {name,age} = person;直接解构赋值，是let name = person.name,左边失去了响应式
    let {name,age} = toRefs(person);
    let n1 = toRef(person,'age')
    function show(){
        name.value += '~'
    }
    function show2(){
        age.value += 1
    }
</script>
<style scoped>
    .person {
        background-color: pink;
        width: 800px;
    }
</style>