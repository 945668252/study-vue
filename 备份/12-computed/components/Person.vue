<template>
    <div class="person">
        姓:<input type="text" v-model="firstNm"><br>
        名:<input type="text" v-model="lastNm"><br>
        全名:{{fullNm}}
        <button @click="show">修改全名</button>
    </div>
</template>
<script lang='ts' setup name="Person">
    import {ref,computed} from 'vue';
    /**
     * computed计算属性是一个函数
     */
    let firstNm = ref('张')
    let lastNm = ref('果汁')
    //这么定义的fullNm是一个计算属性，是只读的
    //fullNm是一个ref响应式对象，改值用.value
    // let fullNm = computed(()=>{
    //     return firstNm.value+lastNm.value
    // })

    //计算属性，加上getter和setter，就是可读可写的
    let fullNm = computed({
        get(){
            return firstNm.value+lastNm.value
        },
        set(val:any){
            let list = val.split('-')
            firstNm.value = list[0];
            lastNm.value = list[1];
        }
    })
    function show(){
        fullNm.value = 'li-si'
    }
</script>
<style scoped>
    .person {
        background-color: pink;
        width: 800px;
    }
</style>