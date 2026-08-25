<template>
  <div class="contacto-container">
    <h1>Contacto - Mercado Ñuble Digital</h1>
    <p>¿Tienes dudas o deseas sumarte como productor? Envíanos un mensaje.</p>

    <!-- Mensaje de error si faltan datos -->
    <div v-if="error" class="alerta error">
      <p>⚠️ {{ error }}</p>
    </div>

    <!-- Mensaje de éxito y resumen de datos -->
    <div v-if="enviado" class="alerta exito">
      <h3>✅ ¡Mensaje enviado con éxito!</h3>
      <p><strong>Resumen de la información ingresada:</strong></p>
      <ul>
        <li><strong>Nombre:</strong> {{ formulario.nombre }}</li>
        <li><strong>Correo:</strong> {{ formulario.email }}</li>
        <li><strong>Teléfono:</strong> {{ formulario.telefono }}</li>
        <li><strong>Comuna:</strong> {{ formulario.comuna }}</li>
        <li><strong>Mensaje:</strong> {{ formulario.mensaje }}</li>
      </ul>
    </div>

    <!-- Formulario vinculado mediante v-model -->
    <form @submit.prevent="procesarFormulario" class="formulario">
      <div class="campo">
        <label for="nombre">Nombre completo *</label>
        <input id="nombre" type="text" v-model="formulario.nombre" placeholder="Ej: Juan Pérez" />
      </div>

      <div class="campo">
        <label for="email">Correo electrónico *</label>
        <input id="email" type="email" v-model="formulario.email" placeholder="ejemplo@correo.cl" />
      </div>

      <div class="campo">
        <label for="telefono">Teléfono *</label>
        <input id="telefono" type="tel" v-model="formulario.telefono" placeholder="+56 9 1234 5678" />
      </div>

      <div class="campo">
        <label for="comuna">Comuna *</label>
        <select id="comuna" v-model="formulario.comuna">
          <option value="">Selecciona tu comuna</option>
          <option value="Chillán">Chillán</option>
          <option value="San Carlos">San Carlos</option>
          <option value="Coihueco">Coihueco</option>
          <option value="Portezuelo">Portezuelo</option>
          <option value="Otra">Otra comuna de Ñuble</option>
        </select>
      </div>

      <div class="campo">
        <label for="mensaje">Mensaje *</label>
        <textarea id="mensaje" v-model="formulario.mensaje" rows="4" placeholder="Escribe tu consulta aquí..."></textarea>
      </div>

      <button type="submit" class="btn-enviar">Enviar Mensaje</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const formulario = ref({
  nombre: '',
  email: '',
  telefono: '',
  comuna: '',
  mensaje: ''
})

const error = ref('')
const enviado = ref(false)

const procesarFormulario = () => {
  // Validación de campos obligatorios
  if (!formulario.value.nombre || !formulario.value.email || !formulario.value.telefono || !formulario.value.comuna || !formulario.value.mensaje) {
    error.value = 'Por favor, completa todos los campos obligatorios antes de enviar.'
    enviado.value = false
    return
  }

  // Si pasa las validaciones
  error.value = ''
  enviado.value = true
}
</script>

<style scoped>
.contacto-container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
}
.formulario {
  display: flex;
  flex-direction: column;
  gap: 15px;
  background: #f9f9f9;
  padding: 20px;
  border-radius: 8px;
  border: 1px solid #ddd;
}
.campo {
  display: flex;
  flex-direction: column;
  text-align: left;
}
.campo label {
  font-weight: bold;
  margin-bottom: 5px;
}
.campo input, .campo select, .campo textarea {
  padding: 8px 12px;
  border: 1px solid #ccc;
  border-radius: 4px;
  font-size: 14px;
}
.btn-enviar {
  padding: 10px;
  background-color: #2c3e50;
  color: white;
  border: none;
  border-radius: 4px;
  font-weight: bold;
  cursor: pointer;
}
.btn-enviar:hover {
  background-color: #1a252f;
}
.alerta {
  padding: 12px;
  border-radius: 6px;
  margin-bottom: 15px;
  text-align: left;
}
.alerta.error {
  background-color: #f8d7da;
  color: #721c24;
  border: 1px solid #f5c6cb;
}
.alerta.exito {
  background-color: #d4edda;
  color: #155724;
  border: 1px solid #c3e6cb;
}
.alerta ul {
  margin-top: 8px;
  padding-left: 20px;
}
</style>