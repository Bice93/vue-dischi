<template>
  <div class="container msCardsBox">
    <h1>Lista dei dischi</h1>
    <DiscCard />
  </div>
</template>

<script>
import DiscCard from './DiscCard.vue';

export default {
    components:{
        DiscCard,
    }

}
</script>

<style lang="scss" scoped>
.msCardsBox{
    color: white;
}
</style>