<template>
  <div id="app">
    <img id="test" alt="Vue logo" src="./assets/logo.png" width="25%" />
    <HelloWorld msg="Hello Vue in CodeSandbox" />
    <button @click="test">ok</button>
  </div>
</template>

<script>
import html2pdf from "html-to-pdf-js";
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
  methods: {
    test() {
      var elementHTML = document.getElementById("app");
      var opt = {
        margin: 0,
        filename: "myfile.pdf",
        image: { type: "jpeg", quality: 0.98 },
        html2canvas: { scale: 2 },
        jsPDF: { unit: "in", format: "letter", orientation: "portrait" },
      };

      // New Promise-based usage:
      html2pdf().set(opt).from(elementHTML).save();
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
