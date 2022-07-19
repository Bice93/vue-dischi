<template>
  <header>
    <div class="logo_header">
        <img src="../assets/logo.png" alt="">
    </div>
  </header>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
header{
    background-color: #2e3a46;
    height: 70px;
    padding: 10px;
}

.logo_header{
    width: 50px;
    height: 100%;
        img{
            width: 100%;
            height: 100%;
            object-fit: contain;
        }
}
</style>