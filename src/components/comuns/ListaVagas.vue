<template>
  <div>
    <div class="row mt-5" v-for="(vaga, index) in vagas" :key="index">
      <div class="col">
        <vaga v-bind="vaga" />
      </div>
    </div>
  </div>
</template>

<script>
import Vaga from "./Vaga.vue";
export default {
  name: "ListaVagas",
  components: { Vaga },
  props: {
    vagas: Array,
  },
};
</script>

<style>
</style>