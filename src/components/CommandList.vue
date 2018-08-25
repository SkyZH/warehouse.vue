<template>
<table class="table">
  <thead>
    <tr>
      <td>Commands</td>
    </tr>
  </thead>
  <tbody>
    <tr v-for="(command, index) in commands"
      :key="index">
      <td v-if="command.type == 'move'">
        <span class="badge badge-success mr-1">bot_move</span>
        <samp class="mr-1">{{ command.bot }} move to ({{ command.location.x }}, {{ command.location.y }}, {{ command.location.z }})</samp>
      </td>
    </tr>
  </tbody>
</table>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class CommandList extends Vue 
{
  @Prop() private commands: any;

  mounted() {
  }
}
</script>

<style scoped>
</style>
