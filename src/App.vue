<template>
  <div id="app">
    <div class="container">
      <form>
        <div>
          <label>Ancho</label>
          <input type="number" v-model="width" />
        </div>
        <div>
          <label>Alto</label>
          <input type="number" v-model="height" />
        </div>
        <div>
          <label>Radio</label>
          <input type="number" v-model="radius" />
        </div>
        <div>
          <label>Color</label>
          <input type="color" v-model="color" />
        </div>
        <div>
          <label>Mostrar figura</label>
          <input type="checkbox" v-model="showFigure" />
        </div>
        <div>
          <label>Estilos adicionales</label>
          <input type="text" v-model="additionalStyles" />
        </div>
      </form>
      <div class="figure-container">
        <div
          v-show="showFigure"
          class="figure"
          :style="{
            width: `${width}px`,
            height: `${height}px`,
            borderRadius: `${radius}px`,
            backgroundColor: color,
          }"
          :class="{ 'additional-styles': additionalStyles }"
        ></div>
      </div>
    </div>
  </div>
</template>

<script>
/*  import HelloWorld from './components/HelloWorld.vue' */

export default {
  name: 'App',
  data() {
    return {
      width: 100,
      height: 100,
      radius: 0,
      color: '#ccc',
      showFigure: true,
      additionalStyles: '',
    };
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 50px;
}

form {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

form div {
  margin-bottom: 10px;
}

.figure-container {
  width: 300px;
  height: 300px;
  border: 1px solid #ccc;
  display: flex;
  justify-content: center;
  align-items: center;
}

.figure {
  background-color: #ccc;
}

.additional-styles {
  border: 5px solid green;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
}
</style>
