<template>
  <main>
    <DiscList />
  </main>
</template>

<script>
import DiscList from './DiscList.vue';

export default {

    components:{
        DiscList,
    }
}
</script>

<style lang="scss" scoped>
main{
    background-color: #1e2d3b;
    padding: 20px 0;
}
</style>