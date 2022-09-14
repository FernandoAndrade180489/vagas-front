<template>
  <div>
    <vagas-favoritas />
    <Topo @navegar="componente = $event" />
    <alerta v-if="exibirAlerta">
      <template v-slot:titulo><h5>Titulo do alerta</h5></template>
      <p>Descrição do alerta</p>
    </alerta>
    <conteudo v-if="visibilidade" :conteudo="componente" />
  </div>
</template>

<script>
import Conteudo from "@/components/layouts/Conteudo.vue";
import TopoPadrao from "./components/layouts/TopoPadrao.vue";
import VagasFavoritas from "./components/comuns/VagasFavoritas.vue";
import Alerta from "./components/comuns/Alerta.vue";

export default {
  name: "App",
  data: () => ({
    visibilidade: true,
    componente: "Home",
    exibirAlerta: false,
  }),
  components: {
    Conteudo,
    Topo: TopoPadrao,
    VagasFavoritas,
    Alerta,
  },
  mounted() {
    this.emitter.on("alerta", () => {
      this.exibirAlerta = true;
      setTimeout(() => (this.exibirAlerta = false), 4000);
      console.log("Apresentar Alerta");
    });
  },
};
</script>

<style scoped>
h1 {
  color: red;
}
</style>
