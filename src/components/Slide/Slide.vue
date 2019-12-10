<template>
  <div class="col-md-12">
    <div id="carouselPrincipal" class="carousel slide" data-ride="carousel">
      <ol class="carousel-indicators">
        <li data-target="#carouselPrincipal" data-slide-to="0" class="active"></li>
        <li data-target="#carouselPrincipal" data-slide-to="1"></li>
        <li data-target="#carouselPrincipal" data-slide-to="2"></li>
      </ol>
      <div class="carousel-inner">
        <div
          class="carousel-item"
          v-for="slide in dados.slide"
          :key="slide.id"
          v-bind:class="[slide.id == 0 ? 'active' : '']"
        >
          <img class="d-block w-100" :src="slide.imageUrl" :alt="slide.title" :title="slide.title" />
        </div>
      </div>
      <a class="carousel-control-prev" href="#carouselPrincipal" role="button" data-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="sr-only">Anterior</span>
      </a>
      <a class="carousel-control-next" href="#carouselPrincipal" role="button" data-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="sr-only">Próximo</span>
      </a>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  created() {
    axios
      .get("http://5dee5773b3d17b00146a273c.mockapi.io/fortnite/infos")
      .then(res => {
        this.dados = res.data[0];
      })
      .catch(err => {
        this.erros.push(err);
      });
  },
  data() {
    return {
      erros: [],
      dados: []
    };
  }
};
</script>

<style scoped>
#carouselPrincipal {
  margin: 20px;
}
</style>
