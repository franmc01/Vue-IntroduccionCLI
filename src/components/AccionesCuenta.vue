<template>
  <button @click="accion" :disabled="desactivar">{{ texto }}</button>
</template>

<script>
export default {
  name: "Acciones Cuenta",
  props: {
    texto: String,
    desactivar: {
        type: Boolean,
        default: false
    }
  },
  methods: {
    accion() {
      this.$emit("accion");
    },
  },
};
</script>

<style>
</style>