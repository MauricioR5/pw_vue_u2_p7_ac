<template>
    <h2>{{ encabezado }} :{{ valor2 }}</h2>

    <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputado }}</p>
    <p>{{ numero }} <sup>2</sup> = {{ calcularCuadradoComputado }}</p>
    <div>
        <button @:click="incrementar">+1</button> <!-- @:click es lo mismo que v-on:click -->
        <button v-on:click="decrementar">-1</button>
    </div>
    <div v-if="esVerdad">
        <h1>Feliz Navidad</h1>
    </div>



</template>

<script>
export default {
    data() {
        return {
            numero: this.valor,
            titulo: 'Contador',
        }
    },
    methods: {
        calcularCuadrado() {
            console.log("Entro a calcular")
            return this.numero * this.numero;
        },
        incrementar() {
            this.numero++;
        },
        decrementar() {
            this.numero--;
        }
    },
    computed: {
        calcularCuadradoComputado() {
            console.log("Entro a calcular computado")
            return this.numero * this.numero;
        }
    },
    //Primera forma de declarar un props
    //props: ['encabezado','valor']
    
    //Segunda forma de declarar un props
    props:{
        encabezado:{
            type: String,
            validator: function (value) {
                return !value.includes('A');
            }
        }, 
        valor:Number,
        valor2:{
            type:Number,
            required:false,
            default:77,
            validator(value){
                //Programo bajo mi criterio y retorno true y retorno false cuando no es válido pa mi
                return value <= 77;
            }
        },
        esVerdad:{
            type:Boolean,
            required:true
        },
        arreglo:Array,
        objetoPersona:Object, 
        fecha: Date,       
        
    }
}
</script>

<style>
button {
    background-color: #07700a;
    border-radius: 5px;
    color: white;
    padding: 10px 10px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
}

button:hover {
    background-color: #053808;
}
</style>