<template>
  <div class="container py-4">
    <div class="row">
      <div class="col">
        <pesquisar-vaga />
      </div>
    </div>

    <div class="row mt-5" v-for="(vaga, index) in vagas" :key="index">
      <div class="col">
        <vaga v-bind="vaga" />
      </div>
    </div>

    <div class="row mt-5">
      <indicador
        titulo="Vagas abertas"
        indicador="100"
        bg="bg-dark"
        color="text-white"
      />

      <indicador
        titulo="Profissionais Cadastrados"
        indicador="225"
        bg="bg-dark"
        color="text-white"
      />

      <indicador
        titulo="Visitantes online"
        :indicador="usuariosOnline"
        bg="bg-light"
        color="text-dark"
      />
    </div>
  </div>
</template>
    
<script>
import PesquisarVaga from "../comuns/PesquisarVaga.vue";
import Indicador from "../comuns/Indicador.vue";
import Vaga from "../comuns/Vaga.vue";
export default {
  name: "Home",
  components: { PesquisarVaga, Indicador, Vaga },
  data: () => ({
    usuariosOnline: 0,
    vagas: [],
  }),
  methods: {
    getUsuariosOnline() {
      this.usuariosOnline = Math.floor(Math.random() * 101); // entre 0 e 100
    },
  },
  created() {
    setInterval(this.getUsuariosOnline, 1000); // a cada 1 segundo
  },
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
   
    
<style scoped>
</style>
    