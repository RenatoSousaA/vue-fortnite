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
          v-for="slide in dadosSlide[0].slide"
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
export default {
  props: {
    dadosSlide: Array
  }
};
</script>

<style scoped>
#carouselPrincipal {
  margin: 20px;
}

.carousel-inner {
  box-shadow: 0px 0px 5px 1px #9a9a9ac9;
}
</style>
