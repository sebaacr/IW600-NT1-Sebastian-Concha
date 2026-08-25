<template>
  <div>
    <nav>
      <router-link to="/">Inicio</router-link> | 
      <router-link to="/productos">Productos</router-link> | 
      <router-link to="/productores">Productores</router-link> | 
      <router-link to="/contacto">Contacto</router-link>
    </nav>
    <hr />
    <router-view />
  </div>
</template>

<style>
nav {
  padding: 10px;
  font-family: sans-serif;
}
nav a {
  margin: 0 10px;
  text-decoration: none;
  color: #2c3e50;
  font-weight: bold;
}
nav a.router-link-exact-active {
  color: #42b983;
}
</style>