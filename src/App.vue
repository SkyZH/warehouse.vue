<template>
  <div id="app">
    <div class="container">
      <nav class="navbar navbar-light bg-light">
        <span class="navbar-brand">Warehouse Simulator Visulization</span>
      </nav>
      <Warehouse :current="current" />
      <input type="number" class="form-control my-1" v-model="current">
      <button class="btn btn-block btn-light" v-on:click="current -= 1">Previous</button>
      <button class="btn btn-block btn-light" v-on:click="current += 1">Next</button>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';
import Warehouse from './components/Warehouse.vue';

@Component({
  components: {
    Warehouse
  },
})
export default class App extends Vue {
  private current: number = 0;
}
</script>

<style lang="scss">
@import "bootstrap/scss/bootstrap.scss";

</style>
