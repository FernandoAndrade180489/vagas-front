<template>
  <div>
    <h1>Componente App</h1>
    <Topo />
    <Conteudo />
  </div>
</template>

<script>
import Conteudo from "./components/layouts/Conteudo.vue";
import TopoPadrao from "./components/layouts/TopoPadrao.vue";

export default {
  name: "App",
  components: {
    Conteudo,
    Topo: TopoPadrao,
  },
};
</script>

<style scoped>
  h1 {
    color:red;
  }

</style>
