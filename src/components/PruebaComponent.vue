<template>
    <div id="PruebaComponent">
        <h1>Prueba Component</h1>
        <HijoComponent 
            v-bind:mensaje=elsaludo 
            v-bind:despedida=ladespedida
            v-on:eventoParaPadre = "procesar_evento"
            ></HijoComponent>
        <p>15 Jul 2023</p>
        <p>Mensaje recibido del Hijo: {{  mensajeRecibido }}</p>
    </div>
</template>

<script>
import HijoComponent from '@/components/HijoComponent.vue';
export default{
    name:'PruebaComponent',
    components:{
        HijoComponent,
    },
    data:function(){
        return{
            elsaludo : 'Hola Mundo !!!!!',
            ladespedida: 'Me voy, hasta pronto !!!',
            mensajeRecibido: '',
        }
    },
    methods:{
        procesar_evento:function(valor){
            this.mensajeRecibido = valor;
        }
    },
    computed:{},
    watch:{},
    created(){
    }
}
</script>

<style scoped>
#PruebaComponent{
    background-color:blueviolet;
    color: white;
}
</style>