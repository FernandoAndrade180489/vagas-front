<template>
  <slot :vagas="vagas">
    <div class="row mt-5" v-for="(vaga, index) in vagas" :key="index">
      <div class="col">
        <vaga v-bind="vaga" />
      </div>
    </div>
  </slot>
</template>

<script>
import Vaga from "./Vaga.vue";
export default {
  name: "ListaVagas",
  components: { Vaga },
  data: () => ({
    vagas: [],
  }),
  activated() {
    this.vagas = JSON.parse(localStorage.getItem("vagas"));
  },
  mounted() {
    this.emitter.on("filtrarVagas", (vaga) => {
      const vagas = JSON.parse(localStorage.getItem("vagas"));
      this.vagas = vagas.filter((item) =>
        item.titulo.toLowerCase().includes(vaga.titulo.toLowerCase())
      );
    });
  },
};
</script>

<style>
</style>