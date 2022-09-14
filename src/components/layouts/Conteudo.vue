<template>
  <div>
    <h1>{{ titulo }}</h1>
    <button @click="atualizarComponente()">Atualizar</button>

    <!-- Renderizar de modo dinamico os componentes home e publicar-vaga. O nome tem que seguir o padrão do componente para permitir renderizar -->
    <button @click="conteudo = 'home'">Home</button>
    <button @click="conteudo = 'publicar-vaga'">Publicar Vaga</button>
    <!-- 
      <home></home>
      <publicar-vaga></publicar-vaga> 
    -->
    <keep-alive><component :is="conteudo" /> </keep-alive>
  </div>
</template>
  
<script>
import Home from "@/components/views/Home.vue";
import PublicarVaga from "../views/PublicarVaga.vue";
export default {
  name: "Conteudo",
  components: {
    Home,
    PublicarVaga,
  },
  data: () => ({
    teste: "O componente foi criado",
    titulo: "Componente Conteudo",
    conteudo: "home",
  }),
  methods: {
    atualizarComponente() {
      this.titulo += "*";
    },
  },
  // beforeCreate() {
  //   console.log("Antes de Criar - ", this.teste);
  // },
  // created() {
  //   console.log("Criado - ", this.teste);
  // },
  // beforeMount() {
  //   console.log("Antes de Montar o template - consumir dados de uma API");
  // },
  // mounted() {
  //   console.log("Montado - entrega o HTML no DOM Final");
  // },

  // beforeUpdate() {
  //   console.log("Antes de atualizar");
  // },
  // updated() {
  //   console.log("Atualizado");
  // },
  // beforeUnmount() {
  //   console.log("Antes de desmontar/destruir");
  // },
  // unmounted() {
  //   console.log("Desmontado/destruído");
  // },

  // errorCaptured() {
  //   console.log("Erro capturado");
  // },
  // renderTracked() {
  //   console.log("Re-renderização rastreada");
  // },
  // renderTriggered() {
  //   console.log("Re-renderização acionada");
  // },
  // activated() {
  //   console.log("Componente é ativado");
  // },
  // deactivated() {
  //   console.log("Componente desativado");
  // },
};
</script>
 
  
<style module>
.teste-1 {
  background-color: red;
}
#teste-2 {
  background-color: yellow;
}
</style>
  