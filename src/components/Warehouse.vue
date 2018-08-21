<template>
  <div></div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import * as d3 from 'd3';
import _ from 'lodash';

const data = require('./data.json');
const objects = (data as any).objects;
const B_SIZE = 30, B_MARGIN = 5;

const p = (p: number) => p * B_SIZE + (p + 1) * B_MARGIN;
const c = (c: string) => { switch(c.substring(0, 3)) {
  case "bot": return "#ff5722";
  case "slf": return "#f9a825";
  case "ste": return "#8bc34a";
  default: return "#000000";
}};

@Component
export default class Warehouse extends Vue {
  mounted() {
    const svg = d3.select(this.$el)
      .append('svg')
      .attr('width', 1000)
      .attr('height', 1000)
      .append('g');
    svg.selectAll('.object')
      .data(_.sortBy(objects, (obj: any) => obj.location.z), (obj: any) => obj.id).enter()
        .append('rect')
        .attr('class', 'object')
        .attr('transform', (d: any) => `translate(${p(d.location.x) + d.location.z * 2}, ${p(d.location.y) + d.location.z * 2})`)
        .attr('width', B_SIZE)
        .attr('height', B_SIZE)
        .attr('fill', (d: any) => c(d.id))
        .attr('stroke', "#fff");
  }
}
</script>

<style scoped>
</style>
