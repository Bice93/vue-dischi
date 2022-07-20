<template>
  <div class="container msCardsBox">
    <div class="boxSelect_gender">
      <GenderSearchBar @search="searchInGender"/>
    </div>

    <div class="containerCards">
      <DiscCard
        v-for="(element, index) in filteredGenderList"
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
      filteredGenderList : [],
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
          this.filteredGenderList = this.discsList;
          console.log(this.discsList);
        })
        .catch((error) => {
          console.warn(error);
        });
    },

    searchInGender (value){
      this.filteredGenderList = [...this.discsList].filter( (element) => element.genre.includes(value) );
      console.log(this.filteredGenderList('pop'));
    }
  },

  created() {
    this.getDiscs();
    this.searchInGender();
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