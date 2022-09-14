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
  props: ["titulo", "descricaoVaga", "salario", "modalidade", "tipo", "publicacao"],
};
</script>

<style>
</style>