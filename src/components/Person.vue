<template>
    <div class="person">
        <h1>情况3：监视reactive定义的对象类型数据</h1>
        <h2>姓名:{{person.name}}</h2>
        <h2>年龄:{{person.age}}</h2>
        <button @click="change">修改姓名</button>
        <button @click="change2">修改年龄</button>
        <button @click="change3">修改整个人</button>
    </div>
</template>
<script lang='ts' setup name="Person">
    import {ref,reactive,watch} from 'vue';
    /**
     * watch只能监视四种数据
     * ref定义的,不可定义ref.value的数据，所以不写
     * reactive定义的
     * 函数返回一个值(getter函数)
     * 一个包含上述内容的数组
     * 遇到五个情况：
     * 1.监视ref定义的基本类型数据
     * 2.情况2：监视ref定义的对象类型数据
     */
    let person = reactive({
        name:'张三',
        age:18
    })
    function change(){
        person.name += '~'
    }
    function change2(){
        person.age += 1;
    }
    function change3(){
        Object.assign(person,{name:'李四',age:20})
    }

</script>
<style scoped>
    .person {
        background-color: pink;
        width: 800px;
    }
</style>