<template>
  <div>
     <label> Scegli il genere: </label>
      <select>
        <option value="0">Rock</option>
        <option value="1" @click="log('cliccato')">Pop</option>
        <option value="2">Jazz</option>
        <option value="3">Metal</option>
      </select>
  </div>
</template>

<script>
export default {
    //  data: function(){
        
    //  },

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