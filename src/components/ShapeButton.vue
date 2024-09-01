<template>
  <div class="shape-button-container">
    <select v-model="selectedShape" @change="changeShape">
      <option value="circle">Círculo</option>
      <option value="square">Cuadrado</option>
      <option value="triangle">Triángulo</option>
    </select>

    <div class="button-wrapper">
      <button
          :class="['shape-button', selectedShape]"
          @click="performAction"
      >
        <span class="button-text">{{ buttonText }}</span>
      </button>
    </div>

    <div v-if="showContent" class="content-container">
      <div v-if="selectedShape === 'circle'">
        <h3>Video del Círculo</h3>
        <iframe width="560" height="315" src="https://www.youtube.com/embed/dQw4w9WgXcQ" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
      </div>
      <div v-else-if="selectedShape === 'square'">
        <h3>Imagen del Cuadrado</h3>
        <img src="../assets/qrcode.png" alt="Cuadrado">
      </div>
      <div v-else-if="selectedShape === 'triangle'">
        <h3>Triángulos en Movimiento</h3>
        <div class="triangle-animation">
          <div v-for="i in 5" :key="i" class="moving-triangle" :style="{ animationDelay: `${i * 0.5}s` }"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ShapeButton',
  data() {
    return {
      selectedShape: 'circle',
      showContent: false,
      buttonText: 'Mostrar'
    }
  },
  methods: {
    changeShape() {
      this.showContent = false;
      this.buttonText = 'Mostrar';
    },
    performAction() {
      this.showContent = !this.showContent;
      this.buttonText = this.showContent ? 'Ocultar' : 'Mostrar';
    }
  }
}
</script>

<style scoped>
.shape-button-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}

.button-wrapper {
  width: 100px;
  height: 100px;
  position: relative;
}

.shape-button {
  width: 100%;
  height: 100%;
  border: none;
  color: white;
  font-weight: bold;
  cursor: pointer;
  transition: all 0.3s ease;
  position: absolute;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}

.button-text {
  position: relative;
  z-index: 2;
}

.circle {
  border-radius: 50%;
  background-color: #ff4136;
}

.square {
  border-radius: 0;
  background-color: #0074d9;
}

.triangle {
  background-color: transparent;
  overflow: hidden;
}

.triangle::before {
  content: '';
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 0;
  height: 0;
  border-left: 50px solid transparent;
  border-right: 50px solid transparent;
  border-bottom: 100px solid #2ecc40;
}

.content-container {
  margin-top: 1rem;
  text-align: center;
}

.triangle-animation {
  position: relative;
  width: 300px;
  height: 300px;
  margin: 0 auto;
}

.moving-triangle {
  position: absolute;
  width: 0;
  height: 0;
  border-left: 25px solid transparent;
  border-right: 25px solid transparent;
  border-bottom: 50px solid #2ecc40;
  animation: moveTriangle 5s infinite linear;
}

@keyframes moveTriangle {
  0% {
    transform: translate(0, 0) rotate(0deg);
  }
  25% {
    transform: translate(100px, 100px) rotate(90deg);
  }
  50% {
    transform: translate(0, 200px) rotate(180deg);
  }
  75% {
    transform: translate(-100px, 100px) rotate(270deg);
  }
  100% {
    transform: translate(0, 0) rotate(360deg);
  }
}
</style>