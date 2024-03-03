<template>
    <div class="person">
        <h1>情况2：监视ref定义的对象类型数据</h1>
        <h2>姓名:{{person.name}}</h2>
        <h2>年龄:{{person.age}}</h2>
        <button @click="change">修改姓名</button>
        <button @click="change2">修改年龄</button>
        <button @click="change3">修改整个人</button>
    </div>
</template>
<script lang='ts' setup name="Person">
    import {ref,watch} from 'vue';
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
    let person = ref({
        name:'张三',
        age:18
    })
    function change(){
        person.value.name += '~'
    }
    function change2(){
        person.value.age += 1;
    }
    function change3(){
        person.value = {name:'李四',age:20}
    }
    //watch(被监视数据，回调，配置对象{})
    watch(person,(newv,oldv)=>{
        console.log('情况1：监视的是对象的地址值',newv,oldv);
    })
    //若想监视对象内部单个属性的变化，需要开启深度监视
    watch(person,(newv,oldv)=>{
        console.log('在对象中开启深度监视且调用立即执行参数',newv,oldv);
        //立即执行：新值是当前值，旧值是undefined
    },{deep:true,immediate:true})
    /**
     * 有情况：newValue 和oldValue大多数情况下相等
     * 因为对象地址没改变，当watch找到新值旧值时，变量已经变为一样
     * 若重新赋值对象（改变地址）则新旧值会不一样
     * 通常情况，只写一个value，oldValue和newValue都是新值
     */

</script>
<style scoped>
    .person {
        background-color: pink;
        width: 800px;
    }
</style>