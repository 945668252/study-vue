<template>
    <div class="person">
        <h1>情况1：监视ref定义的基本类型数据</h1>
        <h2>求和数:{{sum}}</h2>
        <button @click="change">修改数字</button>
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
     * 
     */
    let sum = ref(0);
    function change(){
        sum.value += 1;
    }
    //监视watch(谁，回调函数)
    //如何停止监视？
    let stop = watch(sum,(newVal,oldVal)=>{//不能监视sum.value
        console.log(newVal,'新值');
        console.log(oldVal,'旧值');
        if(newVal>5){
            stop();
        }
    })
</script>
<style scoped>
    .person {
        background-color: pink;
        width: 800px;
    }
</style>