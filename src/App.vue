<template>
  <div>
    <h1>Componente App</h1>
    <button @click="desmontarComponente()">
      Desmontar componente conteudo
    </button>
    <Topo :funcaoCallback="acao" />
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
    acao(p1, p2) {
      console.log(
        "Função de callback definida no componente Pai e chamada no componente Filho"
      );
      console.log("P1: ", p1);
      console.log("P2: ", p2);
    },
  },
};
</script>

<style scoped>
h1 {
  color: red;
}
</style>
