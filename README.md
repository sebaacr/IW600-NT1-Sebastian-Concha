# Mercado Ñuble Digital

## Estudiante
Sebastian Concha

## Descripción
Prototipo frontend de una plataforma para que productores de la Región de Ñuble puedan mostrar y ofrecer sus productos locales.

## Parte A - Estructura y navegación
Se creó la estructura base del proyecto con Vue 3. Se implementó Vue Router para la navegación entre las vistas Inicio, Productos, Productores y Contacto sin recargar la página.

## Parte B - Componentes y Props
Se creó el componente reutilizable `ProductoCard.vue` ubicado en `src/components/`. Este componente recibe un objeto `producto` a través de **Props** que contiene los atributos: nombre, categoría, productor, comuna y precio. La vista principal `Productos.vue` actúa como componente padre, definiendo un arreglo reactivo con 6 productos representativos de distintas comunas de Ñuble (San Carlos, Coihueco, Chillán y Portezuelo) y renderizándolos mediante la iteración del componente hijo.

## Parte C - Listas y condicionales
Se implementó un filtro dinámico por comuna utilizando la directiva `v-model` vinculada a un elemento `<select>`. La lista de productos se genera dinámicamente mediante la directiva `v-for` a partir de una propiedad computada (`computed`) que filtra los datos reactivos. Adicionalmente, se incorporó lógica condicional mediante `v-if` y `v-else`: si existen coincidencias se despliega la cuadrícula de productos, y si no hay resultados disponibles (como al seleccionar Pemuco), la aplicación muestra un mensaje informativo al usuario.

## Parte D - Comunicación mediante Emit
(Pendiente)

## Parte E - Formulario y validación
(Pendiente)

## Parte F - Diseño y presentación
(Pendiente)

## Tecnologías utilizadas
Vue 3, Vite, Vue Router, JavaScript, HTML, CSS.

## Ejecución
1. Clonar el repositorio.
2. Ejecutar `npm install`.
3. Ejecutar `npm run dev`.

## Reflexión final
(Pendiente para el final de la prueba)