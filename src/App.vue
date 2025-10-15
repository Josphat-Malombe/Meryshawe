<script setup>
import Appbar from './components/appbar.vue'
import Footer from './components/Footer.vue'
import ChatAgent from './components/ChatAgent.vue'
import { RouterView } from 'vue-router'
</script>

<template>
  <div class="app-container">
    <Appbar />
    <main class="page-content">
      <RouterView />
    </main>
    <ChatAgent />
    <Footer />
  </div>
</template>

<style>
html,
body {
  margin: 0;
  padding: 0;
  height: 100%;
  width: 100%;
  max-width: 100vw;
}
</style>

<style scoped>
.app-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  width: 100%;
  margin: 0;
  padding: 0;
}

.page-content {
  flex: 1;
  width: 100%;
  padding: 0;
  background-color: #fff;
  margin: 0;
  overflow-x: hidden;
}
</style>
