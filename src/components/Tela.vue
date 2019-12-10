<template>
  <div>
    <slide :dadosSlide="[dados]"></slide>
    <timeLine :dadosTimeLine="[dados]"></timeLine>
  </div>
</template>

<script>
import Slide from "./Slide/Slide";
import TimeLine from "./TimeLine/TimeLine";
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
  components: {
    slide: Slide,
    timeLine: TimeLine
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
.img {
  border-radius: 5px;
  box-shadow: 0px 0px 10px -1px #ccc;
  width: 250px;
  margin: 10px;
}

ul {
  padding-left: 0;
}

li {
  list-style-type: none;
}

button {
  padding: 5px 25px;
}
</style>
