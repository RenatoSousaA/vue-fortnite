<template>
  <div>
    <slide></slide>
  </div>
</template>

<script>
// import axios from "axios";
import Slide from "./Slide/Slide";

export default {
  components: {
    "slide": Slide
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
