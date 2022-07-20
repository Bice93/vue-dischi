<template>
  <div class="container msCardsBox">
    <div class="boxSelect_gender">
      <GenreSearchBar :GenreElement="filterGenreList"/>
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
import GenreSearchBar from "./GenreSearchBar.vue";

export default {
  components: {
    DiscCard,
    GenreSearchBar,
  },

  data: function () {
    return {
      discsList: [],
      filterGenreList : [],
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

          //RECUPERO TUTTI I GENERI
          this.discsList.forEach(element => {
            if(!this.filterGenreList.includes(element.genre)) {
              this.filterGenreList.push(element.genre);
            }
          });
          console.log(this.filterGenreList);
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