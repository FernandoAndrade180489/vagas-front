<template>
  <div>
    <h1>Componente App</h1>
    <button @click="desmontarComponente()">
      Desmontar componente conteudo
    </button>
    <Topo @nomeDoEventoCapturadoNoComponentePai="$event('Texto 1', 125)" />
    <Conteudo v-if="visibilidade" />
  </div>
</template>

<script>
import Conteudo from "@/components/layouts/Conteudo.vue";
import TopoPadrao from "./components/layouts/TopoPadrao.vue";

export default {
  name: "App",
  data: () => ({
    visibilidade: true,
  }),
  components: {
    Conteudo,
    Topo: TopoPadrao,
  },
  methods: {
    desmontarComponente() {
      this.visibilidade = false;
    },
    acao(e) {
      console.log("Componente pai", e);
    },
  },
};
</script>

<style scoped>
h1 {
  color: red;
}
</style>
