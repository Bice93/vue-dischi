<template>
  <div>
     <label> Scegli il genere: </label>
      <select v-model="genreValue">
        <option v-for="genre in GenreElement" :value="genre"> {{ genre }}</option>
        <!-- <option value="1">Pop</option>
        <option value="2">Jazz</option>
        <option value="3">Metal</option> -->
      </select>
  </div>
</template>

<script>
export default {
    props: ['GenreElement'],

     data: function(){
        return{
            genreValue: '',
        }
        
    },

    methods: {
        log(arg){
            console.log(arg)
        }
    }
}
</script>

<style lang="scss" scoped>
.boxSelect_gender select{
    background-color: #2e3a46;
    border: 1px solid #2e3a46;
    color: white;
    width: 150px;
    height: 25px;
}
</style>