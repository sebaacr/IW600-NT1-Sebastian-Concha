<template>
  <div class="card">
    <h3>{{ producto.nombre }}</h3>
    <p><strong>Categoría:</strong> {{ producto.categoria }}</p>
    <p><strong>Productor:</strong> {{ producto.productor }}</p>
    <p><strong>Comuna:</strong> {{ producto.comuna }}</p>
    <p class="precio"><strong>Precio:</strong> ${{ producto.precio.toLocaleString('es-CL') }}</p>
    
    <!-- Botón que desencadena el evento hacia el padre -->
    <button class="btn-interes" @click="manifestarInteres">
      ❤️ Me interesa
    </button>
  </div>
</template>

<script setup>
const props = defineProps({
  producto: {
    type: Object,
    required: true
  }
})

// Declaración del evento emit
const emit = defineEmits(['manifestar-interes'])

const manifestarInteres = () => {
  emit('manifestar-interes', props.producto.nombre)
}
</script>

<style scoped>
.card {
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 16px;
  background-color: #ffffff;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.precio {
  color: #2c3e50;
  font-weight: bold;
}
.btn-interes {
  margin-top: 12px;
  padding: 8px 12px;
  background-color: #27ae60;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
  transition: background-color 0.2s;
}
.btn-interes:hover {
  background-color: #219150;
}
</style>