<template>
  <div id="app-container">
    <header class="header">
      <div class="logo">
        <span>🌱 Mercado Ñuble Digital</span>
      </div>
      <nav class="nav-links">
        <router-link to="/">Inicio</router-link>
        <router-link to="/productos">Productos</router-link>
        <router-link to="/productores">Productores</router-link>
        <router-link to="/contacto">Contacto</router-link>
      </nav>
    </header>

    <main class="main-content">
      <router-view />
    </main>

    <footer class="footer">
      <p>Mercado Ñuble Digital &copy; 2026 - Universidad Adventista de Chile</p>
    </footer>
  </div>
</template>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #f8f9fa;
  color: #2c3e50;
}
#app-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}
.header {
  background-color: #1b5e20;
  color: white;
  padding: 15px 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}
.logo {
  font-size: 1.3rem;
  font-weight: bold;
}
.nav-links {
  display: flex;
  gap: 15px;
}
.nav-links a {
  color: #e8f5e9;
  text-decoration: none;
  font-weight: 600;
  padding: 6px 12px;
  border-radius: 4px;
  transition: background-color 0.2s;
}
.nav-links a:hover, .nav-links a.router-link-exact-active {
  background-color: #2e7d32;
  color: #ffffff;
}
.main-content {
  flex: 1;
  padding: 20px;
}
.footer {
  background-color: #2c3e50;
  color: #bdc3c7;
  text-align: center;
  padding: 15px;
  font-size: 0.85rem;
  margin-top: auto;
}
@media (max-width: 600px) {
  .header {
    flex-direction: column;
    gap: 10px;
    text-align: center;
  }
}
</style>