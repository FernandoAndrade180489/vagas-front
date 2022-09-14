<template>
  <div class="container py-4">
    <div class="row">
      <div class="col">
        <pesquisar-vaga />
      </div>
    </div>

    <div class="row mt-5">
      <div class="col-4">
        <div class="h-100 p-5 rounded-3 border bg-dark text-white">
          <p>Vagas abertas</p>
          <h2>25</h2>
        </div>
      </div>

      <div class="col-4">
        <div class="h-100 p-5 rounded-3 border bg-dark text-white">
          <p>Profissionais Cadastrados</p>
          <h2>125</h2>
        </div>
      </div>

      <div class="col-4">
        <div class="h-100 p-5 rounded-3 border bg-light text-dark">
          <p>Visitantes online</p>
          <h2>15</h2>
        </div>
      </div>
    </div>
  </div>
</template>
    
<script>
import PesquisarVaga from "../comuns/PesquisarVaga.vue";
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
  components: { PesquisarVaga },
};
</script>
   
    
<style scoped>
</style>
    