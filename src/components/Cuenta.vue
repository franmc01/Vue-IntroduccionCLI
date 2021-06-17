<template>
  <h1>Tipo de cuenta: {{ tipo }}</h1>
  <h2>Saldo: ${{ saldo }}</h2>
  <h3>Cuenta: {{ estado ? "Activa" : "Inactiva" }}</h3>
  <div v-for="servicio in servicios" :key="servicio.id">
    {{ servicio }}
  </div>
  <h4>Acciones cuenta</h4>
  <AccionesCuenta texto="Aumentar" />
  &nbsp;
  <AccionesCuenta texto="Disminuir" />
  <!-- <div v-for="(servicio, index) in servicios" :key="index">
    {{ servicio }}
  </div> -->
</template>

<script>
import AccionesCuenta from "./AccionesCuenta.vue";

export default {
  name: "Cuenta",
  components: {
    AccionesCuenta,
  },
  data() {
    return {
      saldo: 2000,
      tipo: "Corriente",
      estado: true,
      servicios: ["Retiro", "Deposito", "Préstamo"],
    };
  },
  methods: {
    aumentar() {
      this.saldo = this.saldo + 100;
    },
    disminuir() {
      this.saldo = this.saldo - 100;
    },
  },
};
</script>

<style>
</style>