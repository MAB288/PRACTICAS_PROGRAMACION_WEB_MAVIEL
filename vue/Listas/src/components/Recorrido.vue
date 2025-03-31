<script>
export default {
    data() {
        return {
          //datos de alumnos
          alumnos:[
            {nc:21620118, nombre: 'Maviel', carrera: 'isc', gustos:'futbol'},
            {nc:21620118, nombre: 'pedro', carrera: 'tics', gustos: 'tenis'},
            {nc:21620118, nombre: 'juan', carrera: 'isc' ,  gustos: 'tenis'},
            {nc:21620118, nombre: 'juan', carrera: 'isc' ,  gustos: 'tenis'},
            {nc:21620118, nombre: 'juan', carrera: 'isc' ,  gustos: 'tenis'},
        ]  

        }
    },
            
}


</script>
<template>
    <div class="container">
        <h3 class="mt-4text">lista de alumnos</h3>
        <ul>
            <li v-for="alumno in alumnos" :key="alumno.nc">
                <strong>{{ alumno.nc }} -</strong>
                <strong>{{ alumno.nombre }} -</strong>
                <strong>{{ alumno.carrera }} -</strong>
                <strong>{{ alumno.gustos }} -</strong>
            </li>
        </ul>
    </div>
</template>
<style>
h3{
    color:rgb(233, 233, 233);
    background-color: black;
    border-radius: 15px;
    padding: 10px;
    text-align: center;
}
ul{
    list-style-type: none;
    padding:0%;
    background-color: black;
    padding: 20px;
}

li{
    color: rgb(235, 235, 235);
    background-color: rgb(19, 64, 199);
    border-radius: 15px;
    padding: 10px;
    margin: 10px;
    text-align: center;
}
</style>