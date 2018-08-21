<template>
  <div id="app">
    <div class="container">
      <nav class="navbar navbar-light bg-light">
        <span class="navbar-brand">Warehouse Simulator Visulization</span>
      </nav>
      <Warehouse :current="current" />
      <input type="number" class="form-control" v-model="current">
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator';
import Warehouse from './components/Warehouse.vue';

@Component({
  components: {
    Warehouse,
  },
})
export default class App extends Vue {
  private current: number = 0;
}
</script>

<style lang="scss">
@import "bootstrap/scss/bootstrap.scss";

</style>
