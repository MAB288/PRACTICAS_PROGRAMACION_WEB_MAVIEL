<template>
  <div class="background">
    <div class="container mt-5">
      <div class="card shadow-lg table-container">
        <div class="card-header bg-dark text-white text-center p-3">
          <h3 class="mb-0 text-uppercase">
            <i class="bi bi-calendar-week me-2"></i>HORARIO DE CLASES SISTEMAS</h3>
        </div>
        <div class="card-body p-0">
          <div class="table-responsive">
            <table class="table table-bordered table-hover mb-0 text-center">
              <thead class="table-primary text-dark">
                <tr>
                  <th v-for="(header, i) in headers" :key="i">{{ header }}</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="(h, index) in Horario" :key="index" class="align-middle">
                  <td class="fw-bold text-center bg-secondary text-white border-black">{{ h.hora }}</td>
                  <td v-for="(day, i) in days" :key="i" :class="['border-black', getCellClass(day, h[day])]">
                    {{ h[day] || '' }}
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const headers = ['Hora', 'Lunes', 'Martes', 'Miércoles', 'Jueves', 'Viernes'];
const days = ['lunes', 'martes', 'miercoles', 'jueves', 'viernes'];

const Horario = ref([
  { hora: '7:00 - 9:00', lunes: 'Programación Lógica y Funcional', martes: 'Inteligencia Artificial', miercoles: '', jueves: 'Programación Lógica y Funcional', viernes: '' },
  { hora: '9:00 - 11:00', lunes: '', martes: '', miercoles: '', jueves: '', viernes: '' },
  { hora: '11:00 - 13:00', lunes: 'Redes de computadoras', martes: '', miercoles: 'Redes De Computadoras', jueves: 'Inteligencia Artificial', viernes: '' },
  { hora: '13:00 - 14:00', lunes: '', martes: '', miercoles: '', jueves: '', viernes: 'Redes De Computadoras' },
  { hora: '13:00 - 15:00', lunes: '', martes: '', miercoles: 'Programacion Web', jueves: 'Administracion De Bases De Datos', viernes: '' },
  { hora: '15:00 - 16:00', lunes: '', martes: '', miercoles: '', jueves: '', viernes: 'Programacion Web' },
  { hora: '16:00 - 17:00', lunes: '', martes: '', miercoles: '', jueves: '', viernes: 'Administracion De Bases De Datos' },
  { hora: '15:00 - 17:00', lunes: 'Programacion Web', martes: 'Taller De Sistemas Operativos', miercoles: '', jueves: 'Taller De Sistemas Operativos', viernes: '' },
  { hora: '17:00 - 19:00', lunes: 'Administracion De Bases De Datos', martes: 'Lenguajes De Interfaz', miercoles: '', jueves: 'Lenguajes De Interfaz', viernes: '' },
  
]);

const getCellClass = (day, value) => {
  if (!value) return 'bg-light';
  return {
    lunes: 'bg-info text-white',
    martes: 'bg-success text-white',
    miercoles: 'bg-warning text-dark',
    jueves: 'bg-danger text-white',
    viernes: 'bg-purple text-white'
  }[day] || '';
};
</script>

<style scoped>

/* Fondo semi-transparente para la tabla */
.table-container {
  background: rgba(255, 255, 255, 0.9); /* Blanco con opacidad */
  border-radius: 10px;
  padding: 20px;
}

/* Bordes negros */
.table td, .table th {
  vertical-align: middle;
  min-width: 150px;
  white-space: nowrap;
  border: 2px solid black !important;
}

/* Colores de encabezados */
.table-primary {
  background-color: #e3ce16 !important;
}

/* Bordes en negro */
.border-black {
  border: 2px solid black !important;
}


.background {
  background-color: #3399d0; /* Color gris claro */
  height: 100vh; /* Ocupar toda la pantalla */
  display: flex;
  align-items: center;
  justify-content: center;
}

/* Centrar el contenedor y agregar fondo */
.table-container {
  background-color: #f0f0f0; /* Color de fondo gris claro */
  padding: 20px;
  border-radius: 10px; /* Bordes redondeados */
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2); /* Sombra */
  max-width: 800px; /* Ancho máximo */
  margin: auto; /* Centra horizontalmente */
  text-align: center; /* Asegura que el contenido interno esté centrado */
}

/* Centrar el encabezado */
.card-header {
  background-color: #000000 !important; /* Color azul */
  color: white !important; /* Texto blanco */
  
}
.table-container {
  background-color: #ffffff; /* Color de fondo blanco */
  padding: 40px; /* Aumentar el espacio interno */
  border-radius: 10px; /* Bordes redondeados */
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2); /* Sombra */
  max-width: 2000px; /* Ancho máximo aumentado */
  min-height: 400px; /* Altura mínima aumentada */
  margin: auto; /* Centra horizontalmente */
  text-align: center; /* Asegura que el contenido interno esté centrado */
}


</style>
