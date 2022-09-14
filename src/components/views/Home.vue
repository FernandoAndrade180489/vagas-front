<template>
  <div class="container py-4">
    <div class="row">
      <div class="col">
        <pesquisar-vaga />
      </div>
    </div>

    <lista-vagas />

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
import ListaVagas from "../comuns/ListaVagas.vue";
export default {
  name: "Home",
  components: { PesquisarVaga, Indicador, ListaVagas },
  data: () => ({
    usuariosOnline: 0,
  }),
  methods: {
    getUsuariosOnline() {
      this.usuariosOnline = Math.floor(Math.random() * 101); // entre 0 e 100
    },
  },
  created() {
    setInterval(this.getUsuariosOnline, 1000); // a cada 1 segundo
  },
  
};
</script>
   
    
<style scoped>
</style>
    