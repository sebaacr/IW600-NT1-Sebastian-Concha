<template>
  <div class="inicio-container">
    <div class="hero">
      <h1>🌾 Mercado Ñuble Digital</h1>
      <p>Conectando a los pequeños productores y emprendedores de la Región de Ñuble con la comunidad.</p>
      <router-link to="/productos" class="btn-hero">Ver Catálogo de Productos</router-link>
    </div>

    <div class="caracteristicas">
      <div class="card-info">
        <h3>📍 Múltiples Comunas</h3>
        <p>Encuentra productos provenientes de San Carlos, Coihueco, Chillán, Portezuelo y más.</p>
      </div>
      <div class="card-info">
        <h3>🍯 100% Local y Artesanal</h3>
        <p>Miel, lácteos, hortalizas, frutas, artesanías y conservas elaboradas directamente por emprendedores locales.</p>
      </div>
      <div class="card-info">
        <h3>🤝 Contacto Directo</h3>
        <p>Manifiesta tu interés o comunícate directamente con la organización para adquirir productos.</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.inicio-container {
  padding: 20px;
  max-width: 1000px;
  margin: 0 auto;
}
.hero {
  background: linear-gradient(135deg, #1b5e20, #2e7d32);
  color: white;
  padding: 40px 20px;
  border-radius: 12px;
  margin-bottom: 30px;
  box-shadow: 0 4px 6px rgba(0,0,0,0.1);
}
.hero h1 {
  font-size: 2.2rem;
  margin-bottom: 10px;
}
.btn-hero {
  display: inline-block;
  margin-top: 15px;
  padding: 10px 20px;
  background-color: #fbc02d;
  color: #333;
  font-weight: bold;
  text-decoration: none;
  border-radius: 6px;
}
.caracteristicas {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
}
.card-info {
  background: #f4f6f8;
  padding: 20px;
  border-radius: 8px;
  border-left: 4px solid #2e7d32;
  text-align: left;
}
</style>