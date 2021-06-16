<template>
  <h1>Tipo de cuenta: {{ tipo }}</h1>
  <h2>Saldo: ${{ saldo }}</h2>
  <h3>Cuenta: {{ estado ? "Activa" : "Inactiva" }}</h3>
  <div v-for="servicio in servicios" :key="servicio.id">
    {{ servicio }}
  </div>
  <!-- <div v-for="(servicio, index) in servicios" :key="index">
    {{ servicio }}
  </div> -->
</template>

<script>
export default {
  name: "Cuenta",
  data() {
    return {
      saldo: 2000,
      tipo: "Corriente",
      estado: true,
      servicios: ["Retiro", "Deposito", "Préstamo"],
    };
  },
};
</script>

<style>
</style>