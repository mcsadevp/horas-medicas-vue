<template>
  <div id="app">
    <h1>Administrador de Citas Médicas</h1>
    <div>
      <FormCitas @agregar="agregarCita" :citas="citas" />
    <hr>
    <ListaCitas :citas="citas" @eliminar="eliminarCita" />
    </div>  
  </div>
</template>
<script>
import FormCitas from './components/FormCitas.vue';
import ListaCitas from './components/ListaCitas.vue';

export default {
  name: 'App',
  components: {
    FormCitas,
    ListaCitas
  },
  data() {
    return {
      citas: []
    };
  },
  methods: {
    agregarCita(nuevaCita) {
      this.citas.push(nuevaCita);
    },
    eliminarCita(index) {
      this.citas.splice(index, 1);
    }
  }
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  margin: 0 auto;
  padding: 20px;
}
h1 {
  color: #333;
  text-align: center
}
hr {
  margin-top: 2px;
  margin-bottom: 2px;
  border: 0;
  border-top: 1px solid #ccc;
  display:flex;

}

</style>