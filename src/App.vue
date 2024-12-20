<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <Contador 
  encabezado="ContAdor Primero" 
  :valor="calcular(1, 2)" 
  :esVerdad="muestra1" 
  :valor2="70" />

  <Contador 
  encabezado=" Segundo" 
  :valor="calcular(5, 4)" 
  :esVerdad="muestra2"/>

  <button @:click="cambiar(1)">Cambiar Primero</button>
  <button @:click="cambiar(2)">Cambiar Segundo</button>
</template>

<script>
import Contador from './components/Contador.vue'
export default {
  name: 'App',
  components: {
    Contador
  },
  methods: {
    calcular(a, b) {
      return a + b;
    },
    cambiar(valor) {
      if(valor===1){
        this.muestra1 = !this.muestra1;
      }else{
        this.muestra2 = !this.muestra2;
    }
    this.muestra = !this.muestra;
  }
  },
  data() {
    return {
      muestra:true,
      muestra1: true,
      muestra2: true,

    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
