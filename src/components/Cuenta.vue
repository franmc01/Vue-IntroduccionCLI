<template>
  <h1>Tipo de cuenta: {{ tipo }}</h1>
  <h2>Saldo: ${{ saldo }}</h2>
  <h3>Cuenta: {{ estado ? "Activa" : "Inactiva" }}</h3>
  <div v-for="servicio in servicios" :key="servicio.id">
    {{ servicio }}
  </div>
  <h4>Acciones cuenta</h4>
  <AccionesCuenta texto="Aumentar" @accion="aumentar"/>
  &nbsp;
  <AccionesCuenta texto="Disminuir" @accion="disminuir" :desactivar="desactivar" />
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
      saldo: 600,
      tipo: "Corriente",
      estado: true,
      servicios: ["Retiro", "Deposito", "Préstamo"],
      desactivar: false
    };
  },
  methods: {
    aumentar() {
      this.saldo = this.saldo + 100;
      this.desactivar = false;
    },
    disminuir() {
      if (this.saldo === 0) {
        this.desactivar = true;
        return;
      }
      this.saldo = this.saldo - 100;
    },
  },
};
</script>

<style>
</style>