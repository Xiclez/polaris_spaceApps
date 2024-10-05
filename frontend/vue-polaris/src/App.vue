<template>
  <div id="app">
    <h1>Star Coordinates and Audio Processor</h1>
    <div>
      <label for="interval">Intervalo entre notas (ms):</label>
      <input v-model="interval" type="number" id="interval" placeholder="350" />
    </div>

    <div>
      <label for="limit">Limitar estrellas:</label>
      <input type="checkbox" v-model="limitStars" id="limit" />
      <input v-model="starLimit" v-if="limitSatrs" type="number" placeholder="Número máximo de estrellas" />
    </div>

    <div>
      <button @click="uploadImage">Subir Imagen</button>
      <button @click="processImage">Procesar Imagen</button>
    </div>

    <div>
      <button @click="openAudio">Abrir Archivo de Audio</button>
      <button @click="cancelProcessing">Cancelar Procesamiento</button>
    </div>

    <div>
      <h2>Imágenes Precargadas:</h2>
      <div v-for="image in predefinedImages" :key="image.name">
        <button @click="openPredefinedImage(image.path)">{{ image.name }}</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      interval: 350,
      limitStars: false,
      starLimit: null,
      predefinedImages: [
        { name: "Imagen 1", path: "/path-to-images/imagen1.jpg" },
        { name: "Imagen 2", path: "/path-to-images/imagen2.jpeg" },
      ],
    };
  },
  methods: {
    uploadImage() {
      // Logic for uploading image will go here
      console.log("Image uploaded");
    },
    processImage() {
      // Call the Python backend here to process the image
      console.log("Processing image");
    },
    openAudio() {
      // Logic to open the generated audio file
      console.log("Opening audio");
    },
    cancelProcessing() {
      // Logic to cancel the processing
      console.log("Processing canceled");
    },
    openPredefinedImage(path) {
      // Logic to open a predefined image
      console.log(`Opening predefined image: ${path}`);
    },
  },
};
</script>

<style>
/* Add any styles here */
</style>
