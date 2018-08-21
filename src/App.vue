<template>
  <div id="app">
    <Warehouse />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Warehouse from './components/Warehouse.vue';

@Component({
  components: {
    Warehouse,
  },
})
export default class App extends Vue {}
</script>

<style>
</style>
