<template>
    <h2>{{titulo}}</h2>
   
    <p>{{ numero }} <sup>2</sup> = {{calcularCuadradoComputado}}</p>
    <p>{{ numero }} <sup>2</sup> = {{calcularCuadradoComputado}}</p>
    <div>
      <button v-on:click="incrementar">+1</button>
      <button v-on:click="decrementar">-1</button>
    </div>
   
   
   
  </template>
   
  <script>
  export default {
      data(){
          return{
              numero:10,
              titulo:'Contador',
          }
      },
      methods:{
          calcularCuadrado(){
              console.log("Entro a calcular")
              return this.numero*this.numero;
          },
          incrementar(){
              this.numero++;
          },
          decrementar(){
              this.numero--;
          }
      },
      computed:{
          calcularCuadradoComputado(){
              console.log("Entro a calcular computado")
              return this.numero*this.numero;
          }
      }
  }
  </script>
   
  <style >
   button{
       background-color: #07700a;
       border-radius: 5px;
       color: white;
       padding: 10px 10px;
       text-align: center;
       text-decoration: none;
       display: inline-block;
       font-size: 16px;
   }
   button:hover{
       background-color: #053808;
   }
  </style>