<template>
  <div class="container py-4">
    <div class="row">
      <div class="col">
        <pesquisar-vaga />
      </div>
    </div>

    <div class="row mt-5">
      <indicador titulo="Vagas abertas" indicador="100" bg="bg-dark" color="text-white"/>

      <indicador titulo="Profissionais Cadastrados" indicador="225" bg="bg-dark" color="text-white"/>

      <indicador titulo="Visitantes online" indicador="15" bg="bg-light" color="text-dark"/>
    </div>
  </div>
</template>
    
<script>
import PesquisarVaga from "../comuns/PesquisarVaga.vue";
import Indicador from "../comuns/Indicador.vue";
export default {
  name: "Home",
  created() {
    console.log("Criado - ", this.teste);
  },
  activated() {
    console.log("Componente é ativado");
  },
  deactivated() {
    console.log("Componente desativado");
  },
  beforeUnmount() {
    console.log("Antes de desmontar/destruir");
  },
  unmounted() {
    console.log("Desmontado/destruído");
  },
  components: { PesquisarVaga, Indicador },
};
</script>
   
    
<style scoped>
</style>
    