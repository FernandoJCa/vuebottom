<script setup>
import { ref } from 'vue'
import ShapeButton from './components/ShapeButton.vue'

const title = ref('Aplicación de Botones con Formas')
const description = ref('Explora diferentes formas y acciones con nuestro botón interactivo.')
</script>

<template>
  <div class="app-container">
    <header>
      <h1>{{ title }}</h1>
    </header>

    <main>
      <p class="description">{{ description }}</p>
      <div class="shape-button-wrapper">
        <ShapeButton />
      </div>
    </main>
  </div>
</template>

<style scoped>
.app-container {
  font-family: Arial, sans-serif;
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem;
  text-align: center;
}

header {
  margin-bottom: 2rem;
}

.logo {
  display: block;
  margin: 0 auto 1rem;
}

h1 {
  color: #2c3e50;
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.description {
  color: #34495e;
  font-size: 1.2rem;
  margin-bottom: 2rem;
}

.shape-button-wrapper {
  background-color: #f0f0f0;
  border-radius: 8px;
  padding: 2rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

footer {
  margin-top: 3rem;
  color: #7f8c8d;
  font-size: 0.9rem;
}

@media (min-width: 1024px) {
  .app-container {
    padding: 3rem;
  }

  h1 {
    font-size: 3rem;
  }

  .description {
    font-size: 1.4rem;
  }
}
</style>