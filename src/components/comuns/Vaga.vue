<template>
  <div class="card">
    <div class="card-header bg-dark text-white">{{ titulo }}</div>
    <div class="card-body">
      <p>{{ descricaoVaga }}</p>
    </div>
    <div class="card-footer">
      <small class="text-muted">
        Salário: {{ salario }} | Modalidade: {{ modalidade }} | Tipo:
        {{ tipo }} | Publicação: {{ publicacao }}</small
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "Vaga",
  // props: ["titulo", "descricaoVaga", "salario", "modalidade", "tipo", "publicacao"],
  props: {
    titulo: {
      type: String,
      required: true,
      validator(p) {
        // console.log("Prop:", p, p.length);
        if (p.length < 6) return false; // se estiver inválido
        return true; //se estiver valido
      },
    },
    descricaoVaga: {
      type: String,
      // default: 'O contratante não adicionou uma descrição para essa vaga'
      default() {
        return "*".repeat(20);
      },
    },
    salario: {
      type: [Number, String],
      required: true,
    },
    modalidade: {
      type: String,
      required: true,
    },
    tipo: {
      type: String,
      required: true,
    },
    publicacao: {
      type: String,
      required: true,
    },
  },
  //   created() {
  //     console.log("titulo", typeof this.titulo);
  //     console.log("descricaoVaga", typeof this.descricaoVaga);
  //     console.log("salario", typeof this.salario);
  //     console.log("modalidade", typeof this.modalidade);
  //     console.log("tipo", typeof this.tipo);
  //     console.log("publicacao", typeof this.publicacao);
  //   },
};
</script>

<style>
</style>