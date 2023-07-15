<template>
    <div id="HijoComponent">
        <h1>Hijo Component</h1>
        <p>{{  mensaje }}</p>
        <p>{{  despedida }}</p>

        <form>
            <label for = "txtRespuesta"> Respuesta: </label>
            <input type="text" id="txtRespuesta"  v-model="respuesta_hijo">
            <button v-on:click.prevent="enviar_al_padre"> Enviar al padre</button>
        </form>


        <br>
        <p>{{  respuesta_hijo }} </p>
    </div>
</template>

<script>
export default{
    name:'HijoComponent',
    props:{
        mensaje:{
            type:String,
            default: 'Hola',
            required: true,
        },
        despedida:{
            type: String,
            default: 'adios',
            required: false,
        }
    },
    data:function(){
        return{
            respuesta_hijo: '',
        }
    },
    methods:{
        enviar_al_padre: function(){
            this.$emit('eventoParaPadre', this.respuesta_hijo);
        },
    },
    computed:{},
    watch:{},
    created(){
    }
}
</script>

<style scoped>
#HijoComponent{
    background-color:aqua;
    color: white;
    margin: 3%;
}
</style>