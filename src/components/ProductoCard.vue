<template>
  <div class="card">
    <h3>{{ producto.nombre }}</h3>
    <p><strong>Categoría:</strong> {{ producto.categoria }}</p>
    <p><strong>Productor:</strong> {{ producto.productor }}</p>
    <p><strong>Comuna:</strong> {{ producto.comuna }}</p>
    <p class="precio"><strong>Precio:</strong> ${{ producto.precio.toLocaleString('es-CL') }}</p>
  </div>
</template>

<script setup>
defineProps({
  producto: {
    type: Object,
    required: true
  }
})
</script>

<style scoped>
.card {
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 16px;
  background-color: #ffffff;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
}
.precio {
  color: #2c3e50;
  font-weight: bold;
}
</style>