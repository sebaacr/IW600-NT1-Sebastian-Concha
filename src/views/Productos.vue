<template>
  <div class="catalogo">
    <h1>Catálogo de Productos</h1>
    
    <!-- Notificación visible cuando el padre recibe el $emit -->
    <div v-if="mensajeInteres" class="alerta-confirmacion">
      <p>✅ {{ mensajeInteres }}</p>
    </div>

    <!-- Filtro dinámico por Comuna -->
    <div class="filtro-container">
      <label for="comuna-select"><strong>Filtrar por Comuna: </strong></label>
      <select id="comuna-select" v-model="comunaSeleccionada">
        <option value="">Todas las comunas</option>
        <option value="San Carlos">San Carlos</option>
        <option value="Coihueco">Coihueco</option>
        <option value="Chillán">Chillán</option>
        <option value="Portezuelo">Portezuelo</option>
        <option value="Pemuco">Pemuco (Sin productos)</option>
      </select>
    </div>

    <!-- Renderizado con escucha de evento @manifestar-interes -->
    <div v-if="productosFiltrados.length > 0" class="grid-productos">
      <ProductoCard 
        v-for="item in productosFiltrados" 
        :key="item.id" 
        :producto="item"
        @manifestar-interes="registrarInteres"
      />
    </div>
    
    <div v-else class="mensaje-vacio">
      <p>⚠️ No se encontraron productos disponibles para la comuna seleccionada.</p>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'
import ProductoCard from '../components/ProductoCard.vue'

const comunaSeleccionada = ref('')
const mensajeInteres = ref('')

const productos = ref([
  { id: 1, nombre: 'Miel Orgánica Nativa', categoria: 'Conservas', productor: 'Don Pedro', comuna: 'San Carlos', precio: 6500 },
  { id: 2, nombre: 'Queso Mantecoso Artesanal', categoria: 'Lácteos', productor: 'Quesos Ñuble', comuna: 'Coihueco', precio: 8000 },
  { id: 3, nombre: 'Arándanos Frescos', categoria: 'Frutas', productor: 'Huerto San Antonio', comuna: 'Chillán', precio: 3500 },
  { id: 4, nombre: 'Mermelada de Frutilla', categoria: 'Conservas', productor: 'Doña Elena', comuna: 'San Carlos', precio: 3000 },
  { id: 5, nombre: 'Vino Pipeño Artesanal', categoria: 'Licores', productor: 'Viña El Carmelo', comuna: 'Portezuelo', precio: 5000 },
  { id: 6, nombre: 'Greda Negra Tradicional', categoria: 'Artesanía', productor: 'Alfareras de Quinchamalí', comuna: 'Chillán', precio: 12000 }
])

const productosFiltrados = computed(() => {
  if (!comunaSeleccionada.value) {
    return productos.value
  }
  return productos.value.filter(p => p.comuna === comunaSeleccionada.value)
})

// Función que se ejecuta al recibir el emit del hijo
const registrarInteres = (nombreProducto) => {
  mensajeInteres.value = `Has manifestado interés en: "${nombreProducto}". ¡Pronto nos pondremos en contacto!`
}
</script>

<style scoped>
.catalogo {
  padding: 20px;
}
.alerta-confirmacion {
  background-color: #d4edda;
  border: 1px solid #c3e6cb;
  color: #155724;
  padding: 12px 16px;
  border-radius: 6px;
  margin-bottom: 20px;
}
.filtro-container {
  margin-bottom: 20px;
}
.filtro-container select {
  padding: 8px 12px;
  border-radius: 4px;
  border: 1px solid #ccc;
  font-size: 14px;
}
.grid-productos {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 20px;
}
.mensaje-vacio {
  padding: 20px;
  background-color: #fff3cd;
  border: 1px solid #ffeeba;
  border-radius: 6px;
  color: #856404;
  text-align: center;
  margin-top: 20px;
}
</style>