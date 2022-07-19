<template>
        <div class="card_disc">
            <div class="box_image">
                <img :src="discElement.poster" 
                :alt="`Poster ${discElement.title}-${discElement.author}-${discElement.year}`"/>
            </div>

            <div class="box_info">
                <h4> {{ discElement.title }} </h4>
                <h6> {{ discElement.author }} </h6>
                <h6> {{ discElement.year }} </h6>
            </div>
        </div>
</template>

<script>
export default {
    props: ["discElement"],
};
</script>

<style lang="scss" scoped>

.card_disc {
  background-color: #2e3a46;
  padding: 15px;
  margin: 10px;
  width: calc(100% / 5 - 20px);
  text-align: center;
}

.box_image {
  width: 100%;
  height: 8rem;

  img {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }
}

.box_info h4 {
    font-size: 16px;
  margin: 10px 0;
  text-transform: uppercase;
}

.box_info h6 {
  font-size: 12px;
  font-weight: 300;
  color: #686b6f;
}
</style>