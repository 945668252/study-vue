<template>   
  <div>
    根组件
    子组件：<Person></Person>
  </div>
</template>

<script lang="ts">
  import Person from './components/Person.vue';
  export default {
    name:'App',
    components:{Person},//注册组件
  }

</script>
<style scoped>

</style>
