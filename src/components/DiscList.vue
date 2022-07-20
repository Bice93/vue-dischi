<template>
  <div class="container msCardsBox">
    <div class="boxSelect_gender">
      <GenderSearchBar/>
    </div>

    <div class="containerCards">
      <DiscCard
        v-for="(element, index) in discsList"
        :key="index"
        :discElement="element"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import DiscCard from "./DiscCard.vue";
import GenderSearchBar from "./GenderSearchBar.vue";

export default {
  components: {
    DiscCard,
    GenderSearchBar,
  },

  data: function () {
    return {
      discsList: [],
    };
  },

  methods: {
    getDiscs() {
      //recupero i dati per la lista dei dischi
      //console.log('Recupero i dati')
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((result) => {
          //console.log(result.data.response)
          this.discsList = result.data.response;
          console.log(this.discsList);
        })
        .catch((error) => {
          console.warn(error);
        });
    },
  },

  created() {
    this.getDiscs();
  },
};
</script>

<style lang="scss" scoped>
.boxSelect_gender{
  margin: 30px 0;
}

.containerCards {
  display: flex;
  flex-wrap: wrap;
}

.msCardsBox {
  color: white;
}
</style>