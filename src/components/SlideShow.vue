<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const images = [
  new URL('../assets/images/1.jpeg', import.meta.url).href,
  new URL('../assets/images/2.jpg', import.meta.url).href,
  new URL('../assets/images/3.jpg', import.meta.url).href,
  new URL('../assets/images/4.jpg', import.meta.url).href
]

const current = ref(0)
let intervalId = null

const nextSlide = () => {
  current.value = (current.value + 1) % images.length
}
const prevSlide = () => {
  current.value = (current.value - 1 + images.length) % images.length
}

onMounted(() => {
  intervalId = setInterval(nextSlide, 50000)
})
onUnmounted(() => {
  clearInterval(intervalId)
})
</script>

<template>
  <section class="slideshow">
    <transition name="fade" mode="out-in">
      <img
        :key="images[current]"
        :src="images[current]"
        alt="Slideshow image"
        class="slide-image"
      />
    </transition>

    <button class="nav-btn prev" @click="prevSlide">❮</button>
    <button class="nav-btn next" @click="nextSlide">❯</button>

    <div class="dots">
      <span
        v-for="(img, index) in images"
        :key="index"
        :class="{ active: index === current }"
        class="dot"
        @click="current = index"
      ></span>
    </div>
  </section>
</template>

<style scoped>
.slideshow {
  position: relative;
  width: 100vw;
  height: 90vh;
  overflow: hidden;
  margin: 0;
  left: 50%;
  right: 50%;
  margin-left: -50vw;
  margin-right: -50vw;
}

.slide-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.nav-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background-color: rgba(0, 0, 0, 0.4);
  color: white;
  border: none;
  font-size: 2rem;
  padding: 0.4rem 0.8rem;
  cursor: pointer;
  border-radius: 50%;
  z-index: 5;
  transition: background-color 0.3s;
}
.nav-btn:hover {
  background-color: rgba(0, 0, 0, 0.7);
}
.prev {
  left: 20px;
}
.next {
  right: 20px;
}

.dots {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 10px;
}
.dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background-color: rgba(255, 255, 255, 0.5);
  cursor: pointer;
  transition: background-color 0.3s;
}
.dot.active {
  background-color: #ffcc00;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 1s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
