<template>
  <div>
    <vagas-favoritas />
    <Topo @navegar="componente = $event" />
    <alerta v-if="exibirAlerta" />
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
