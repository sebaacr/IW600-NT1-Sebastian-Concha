<template>
  <div class="catalogo">
    <h1>Catálogo de Productos</h1>
    <div class="grid-productos">
      <ProductoCard 
        v-for="item in productos" 
        :key="item.id" 
        :producto="item" 
      />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import ProductoCard from '../components/ProductoCard.vue'

const productos = ref([
  { id: 1, nombre: 'Miel Orgánica Nativa', categoria: 'Conservas', productor: 'Don Pedro', comuna: 'San Carlos', precio: 6500 },
  { id: 2, nombre: 'Queso Mantecoso Artesanal', categoria: 'Lácteos', productor: 'Quesos Ñuble', comuna: 'Coihueco', precio: 8000 },
  { id: 3, nombre: 'Arándanos Frescos', categoria: 'Frutas', productor: 'Huerto San Antonio', comuna: 'Chillán', precio: 3500 },
  { id: 4, nombre: 'Mermelada de Frutilla', categoria: 'Conservas', productor: 'Doña Elena', comuna: 'San Carlos', precio: 3000 },
  { id: 5, nombre: 'Vino Pipeño Artesanal', categoria: 'Licores', productor: 'Viña El Carmelo', comuna: 'Portezuelo', precio: 5000 },
  { id: 6, nombre: 'Greda Negra Tradicional', categoria: 'Artesanía', productor: 'Alfareras de Quinchamalí', comuna: 'Chillán', precio: 12000 }
])
</script>

<style scoped>
.catalogo {
  padding: 20px;
}
.grid-productos {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 20px;
  margin-top: 20px;
}
</style>