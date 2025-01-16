<template>
    <img :src="imagen" alt="No hay :c">
    <div class="seccion-pregunta">
    <input v-model="pregunta" type="text" placeholder="Hazme una pregunta!">
    <p>Recuerda que cuando finalices tu pregunta, da un ?</p>

    <h1>{{ pregunta }}</h1>
    <h2>{{ respuesta }}</h2>
</div>
</template>

<script>
export default {

    data() {
        return {
            pregunta: 'Hola Mundo',
            respuesta: 'null',
            imagen: 'https://yesno.wtf/assets/yes/14-b57c6dc03aa15a4b18f53eb50d6197ee.gif',
        }
    },
    watch: {
        pregunta(value, oldValue) {
            console.log(value);
            console.log(oldValue);
            if (value.includes('?')) {
                //Programar la llamada a la API para obtener si o no
                //y la imagen
                console.log('Llamando a la API');
                this.fachada();

            }

        }
    },
    methods: {
        async llamarAPI() {
            const data = await fetch('https://yesno.wtf/api').then(respuesta => respuesta.json());
            this.respuesta = data.answer;
            this.imagen = data.image;
            console.log(data);
        },
        async fachada() {
            await this.llamarAPI();
        }
    }
}
</script>

<style>
img {
    max-height: 100%;
    height: 100vh;
    max-width: 100%;
    width: 100vw;
    position: fixed;
    top: 0px;
    left: 0px;
}
.seccion-pregunta {
    position: relative;
}
h1,p, h2{
    text-align: center;
    color: white;
    text-shadow: 2px 2px 4px #000000;
}
p{
    font-size: 30px;
}

input {
margin-top: 35%;
width: 260px;
padding: 15px 30px;
border: none;
border-radius: 7px;
font-size: 18px;
}
</style>