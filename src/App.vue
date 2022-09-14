<template>
  <div>
    <vagas-favoritas />
    <Topo @navegar="componente = $event" />
    <conteudo v-if="visibilidade" :conteudo="componente" />
  </div>
</template>

<script>
import Conteudo from "@/components/layouts/Conteudo.vue";
import TopoPadrao from "./components/layouts/TopoPadrao.vue";
import VagasFavoritas from "./components/comuns/VagasFavoritas.vue";

export default {
  name: "App",
  data: () => ({
    visibilidade: true,
    componente: "Home",
  }),
  components: {
    Conteudo,
    Topo: TopoPadrao,
    VagasFavoritas,
  },
};
</script>

<style scoped>
h1 {
  color: red;
}
</style>
