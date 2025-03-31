<template>
    <div class="container ms-5"> 
        <div class="row mt-4">
            <div>
                <h4>Evento click</h4>
                <button @click="clic" class="btn btn-danger" type="button">dale clic</button>
                <button @click="soyunboton" class="btn btn-warning mx-2" type="button">dale clic</button>
            </div>
            <div>
                <h4>Evento Change</h4>
                <label class="input-group-text" for="">Ingresa tu nombre</label>
                <input class="form-control mt-2" type="text" id="nombre" @change="nombreE">
                <p>nombre ingresado es: <strong>{{ nombre }}</Strong></p> 
            </div>
            <div>
                <h3>Evento de mouseenter y mouseleave</h3>
                <div class="text-center"
                    style="color:white; width: 300px; height: 200px; background-color: black; text-align: center; padding: 15px; border-radius: 15px;"
                    @mouseenter="mostrarmensaje" @mouseleave="ocultarmensaje">
                    <p >pase el mause</p>
                    <p>{{ mensaje }}</p>
                
                 </div>
            </div>
            
        </div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            nombre: '',
            mensaje: '',
        }
    },
    methods: {
        clic() {
            alert("Hola racias por darle clic");
        },
        soyunboton() {
            alert("Hola soy un boton");
        },
        nombreE(event) {
        this.nombre=event.target.value

       },
       mostrarmensaje(){
        this.mensaje="el mause esta dentro del rectangulo"
       },
       ocultarmensaje(){
        this.mensaje ="el mouse esta fuera del rectangulo"
       },
    }
    
}
</script>

<style scoped>
</style>
