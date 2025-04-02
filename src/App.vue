<template>
  <div class="app">
    <Header />
    <main>
      <router-view />
    </main>
    <Footer />
  </div>
</template>

<script setup>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
</script>

<style>
/* Global styles */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  line-height: 1.6;
  color: #333;
  width: 100%;
  margin: 0;
  padding: 0;
  overflow-x: hidden;
}

.app {
  width: 100%;
  min-height: 100vh;
}

main {
  min-height: 80vh;
  width: 100%;
}

img {
  max-width: 100%;
  height: auto;
}
</style>