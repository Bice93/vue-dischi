<template>
  <div>
     <label> Scegli il genere: </label>
      <select>
        <option value="0">Rock</option>
        <option value="1">Pop</option>
        <option value="2">Jazz</option>
        <option value="3">Metal</option>
      </select>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
.boxSelect_gender select{
    padding: 5px;
    background-color: #2e3a46;
    border: 1px solid #2e3a46;
    color: white;
    width: 150px;
    height: 25px;
}
</style>