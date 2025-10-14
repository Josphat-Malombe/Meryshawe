<script setup>
import { ref, onMounted } from "vue";

const images = ref([]); 
const loading = ref(true);

onMounted(() => {
  
  setTimeout(() => {
    loading.value = false;
  }, 1000);
});
</script>

<template>
  <div class="gallery-page">
    <h1 class="title">Photo Gallery</h1>

    <div v-if="loading" class="loading">
      <div class="loader"></div>
      <p>Loading images...</p>
    </div>

    <div v-else>
      <div v-if="images.length === 0" class="coming-soon">
        <p> Our gallery</p>
      </div>

      <div v-else class="gallery-grid">
        <div v-for="(img, i) in images" :key="i" class="photo-card">
          <img
            :src="img"
            alt="Gallery Image"
            loading="lazy"
            class="photo"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.gallery-page {
  font-family: "Poppins", sans-serif;
  background: linear-gradient(to bottom right, #f7f9fc, #eef1f6);
  padding: 70px ;
  text-align: center;
  min-height: 100vh;
}

.title {
  color: maroon;
  font-size: 2.5rem;
  margin-bottom: 2rem;
}

.loading {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 50vh;
}

.loader {
  border: 5px solid #e0e6ed;
  border-top: 5px solid #1a73e8;
  border-radius: 50%;
  width: 45px;
  height: 45px;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}

.loading p {
  color: #555;
  margin-top: 15px;
  font-size: 1rem;
}

.coming-soon {
  padding: 80px 20px;
  border-radius: 12px;
  background: #ffffffaa;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
  font-size: 1.2rem;
  color: #334155;
  backdrop-filter: blur(8px);
}

.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 20px;
  margin-top: 30px;
}

.photo-card {
  position: relative;
  overflow: hidden;
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  background: #e9eef7;
}

.photo-card:hover {
  transform: scale(1.03);
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.1);
}

.photo {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  opacity: 0;
  transition: opacity 0.8s ease-in-out;
}

.photo[loading="lazy"] {
  opacity: 1;
}
</style>
