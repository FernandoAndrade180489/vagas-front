<template>
  <div class="col-4">
    <div class="h-100 p-5 rounded-3 border bg-dark text-white">
      <p>{{titulo}}</p>
      <h2>{{indicador}}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: "Indicador",
  props: ['titulo', 'indicador'],
};
</script>

<style>
</style>