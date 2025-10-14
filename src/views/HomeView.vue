<script setup>
import SlideShow from '@/components/SlideShow.vue'
import Curriculum from '@/components/Curriculum.vue'
import Pillars from '@/components/Pillars.vue'
import Us from '@/components/Us.vue';
import Gallary from '@/components/gallary.vue';


</script>

<template>
  <div class="home">
    <div class="full-width">
      <SlideShow />
    </div>
    <div class="content-section">
      <h1>Empowering Leaders of Purpose and Integrity</h1>
    </div>
    <div class="full-width">
      <Curriculum />
      <pillars/>
      <Us/>
      <Gallary/>
      
    </div>
    

  </div>
</template>

<style scoped>
.home {
  width: 100%;
  min-height: 100%;
  display: flex;
  flex-direction: column;
  background-color: white;
  margin: 0;
  padding: 0;
}

.full-width {
  width: 100%;
  margin: 0;
  padding: 0;
}

.content-section {
  width: 100%;
  padding: 2rem 1rem;
  text-align: center;
}

.home h1 {
  margin: 2rem auto;
  font-size: 2rem;
  color: black;
  font-weight: 600;
  font-family: 'Times New Roman', Times, serif;
  max-width: 1200px;
}
</style>
