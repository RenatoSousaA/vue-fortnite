<template>
  <div class="container py-2 mt-4 mb-4">
    <h1>Timeline</h1>
    <hr />
    <div class="row no-gutters" v-for="timeLine in dadosTimeLine[0].chapters" :key="timeLine.id">
      <div class="col-sm" v-if="timeLine.id % 2 == 0"></div>
      <div class="col-sm-1 text-center flex-column d-none d-sm-flex" v-if="timeLine.id % 2 == 0">
        <div class="row h-50">
          <div class="col" v-bind:class="[timeLine.id != 1 ? 'border-right' : '']">&nbsp;</div>
          <div class="col">&nbsp;</div>
        </div>
        <h5 class="m-2">
          <span class="badge badge-pill bg-light border" style="color: transparent">-</span>
        </h5>
        <div class="row h-50">
          <div
            class="col"
            v-bind:class="[timeLine.id != dadosTimeLine[0].chapters.length ? 'border-right' : '']"
          >&nbsp;</div>
          <div class="col">&nbsp;</div>
        </div>
      </div>
      <div class="col-sm py-2" v-if="timeLine.id % 2 == 0">
        <div class="card">
          <div class="card-body">
            <h4
              class="card-title text-muted text-center"
            >Chapter {{timeLine.chapter}} | Season {{timeLine.season}}</h4>
            <h4 class="text-muted small">
              Duração:
              {{timeLine.start | formatDate}} - {{timeLine.end | formatDate}}
            </h4>
            <a v-bind:href="timeLine.site" target="_blank">
              <img
                class="img-card"
                :src="timeLine.imageUrl"
                :alt="'Season ' + timeLine.season"
                :title="'Season ' + timeLine.season"
              />
            </a>
          </div>
        </div>
      </div>

      <div class="col-sm py-2" v-if="timeLine.id % 2 != 0">
        <div class="card">
          <div class="card-body">
            <h4
              class="card-title text-muted text-center"
            >Chapter {{timeLine.chapter}} | Season {{timeLine.season}}</h4>
            <h4 class="text-muted small">
              Duração:
              {{timeLine.start | formatDate}} - {{timeLine.end | formatDate}}
            </h4>
            <a v-bind:href="timeLine.site" target="_blank">
              <img
                class="img-card"
                :src="timeLine.imageUrl"
                :alt="'Season ' + timeLine.season"
                :title="'Season ' + timeLine.season"
              />
            </a>
          </div>
        </div>
      </div>
      <div class="col-sm-1 text-center flex-column d-none d-sm-flex" v-if="timeLine.id % 2 != 0">
        <div class="row h-50">
          <div class="col" v-bind:class="[timeLine.id != 1 ? 'border-right' : '']">&nbsp;</div>
          <div class="col">&nbsp;</div>
        </div>
        <h5 class="m-2">
          <span class="badge badge-pill bg-light border" style="color: transparent">-</span>
        </h5>
        <div class="row h-50">
          <div
            class="col"
            v-bind:class="[timeLine.id != dadosTimeLine[0].chapters.length ? 'border-right' : '']"
          >&nbsp;</div>
          <div class="col">&nbsp;</div>
        </div>
      </div>
      <div class="col-sm" v-if="timeLine.id % 2 != 0"></div>
    </div>
    <hr />
  </div>
</template>

<script>
import moment from "moment";
export default {
  filters: {
    formatDate: function(value) {
      if (value) {
        return moment(String(value)).format("DD/MM/YYYY");
      }
    }
  },
  props: {
    dadosTimeLine: Array
  }
};
</script>

<style scoped>
.img-card {
  width: 400px;
  height: 200px;
  box-shadow: 0px 0px 5px 3px #828282;
  margin-top: 10px;
  margin-bottom: 5px;
  border-radius: 5px;
}

h1 {
  font-variant: all-small-caps;
  margin: 20px 0;
}

hr {
  border-color: aliceblue;
  margin: 30px 0;
}
</style>
