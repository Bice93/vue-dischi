<template>
  <div class="containerCards">
        <div class="card_disc">
            <div class="box_image">
                <img src="../assets/logo.png" alt="" />
            </div>

            <div class="box_info">
                <h4>Titolo</h4>
                <h6>Autore</h6>
                <h6>Anno</h6>
            </div>
        </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.containerCards {
  display: flex;
  flex-wrap: wrap;
}

.card_disc {
  background-color: #2e3a46;
  padding: 15px;
  margin: 10px;
  width: calc(100% / 6 - 20px);
  text-align: center;
}

.box_image {
  width: 100%;
  height: 7rem;

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}

.box_info h4 {
  margin: 10px 0;
  text-transform: uppercase;
}

.box_info h6 {
  font-size: 13px;
  font-weight: 300;
  color: #686b6f;
}
</style>