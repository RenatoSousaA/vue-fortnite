<template>
  <div class="container py-2 mt-4 mb-4">
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
  </div>
  <!-- <div class="row justify-content-center">
    <div class="col-md-6">
      <ul class="timeline">
        <li
          class="timeline-item bg-white rounded ml-3 p-4 shadow"
          v-for="timeLine in dadosTimeLine[0].chapters"
          :key="timeLine.id"
        >
          <div class="timeline-arrow"></div>
          <h2 class="h5 mb-0 text-gray">Chapter {{timeLine.chapter}} | Season {{timeLine.season}}</h2>
          <span class="small text-gray">
            <i class="fa fa-clock-o mr-1"></i>
            Duração:
            {{timeLine.start | formatDate}} - {{timeLine.end | formatDate}}
          </span>
        </li>
      </ul>
    </div>
  </div>-->
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
</style>
