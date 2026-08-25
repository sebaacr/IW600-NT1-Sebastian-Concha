<template>
  <div class="productores-container">
    <h1>Nuestros Productores de Ñuble</h1>
    <p class="subtitulo">Conoce a las personas y familias detrás de cada producto local.</p>

    <div class="grid-productores">
      <div v-for="p in productores" :key="p.id" class="card-productor">
        <h3>{{ p.nombre }}</h3>
        <p><strong>Comuna:</strong> {{ p.comuna }}</p>
        <p><strong>Especialidad:</strong> {{ p.especialidad }}</p>
        <p class="descripcion">{{ p.descripcion }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const productores = ref([
  { id: 1, nombre: 'Don Pedro', comuna: 'San Carlos', especialidad: 'Miel Orgánica', descripcion: 'Más de 15 años dedicados a la apicultura sustentable en la zona rural de San Carlos.' },
  { id: 2, nombre: 'Quesos Ñuble', comuna: 'Coihueco', especialidad: 'Lácteos Artesanales', descripcion: 'Elaboración tradicional de quesos mantecosos con leche fresca de la precordillera.' },
  { id: 3, nombre: 'Huerto San Antonio', comuna: 'Chillán', especialidad: 'Frutas y Berries', descripcion: 'Cultivo natural de arándanos y frutillas sin pesticidas.' },
  { id: 4, nombre: 'Viña El Carmelo', comuna: 'Portezuelo', especialidad: 'Vinos de Autor', descripcion: 'Tradicíon vitivinícola patrimonial del Valle del Itata.' }
])
</script>

<style scoped>
.productores-container {
  padding: 20px;
  max-width: 1000px;
  margin: 0 auto;
}
.subtitulo {
  color: #666;
  margin-bottom: 25px;
}
.grid-productores {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 20px;
}
.card-productor {
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 18px;
  background: white;
  text-align: left;
  box-shadow: 0 2px 4px rgba(0,0,0,0.04);
}
.card-productor h3 {
  color: #1b5e20;
  margin-bottom: 8px;
}
.descripcion {
  font-size: 0.9rem;
  color: #555;
  margin-top: 8px;
}
</style>