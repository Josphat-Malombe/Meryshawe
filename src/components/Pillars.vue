<script setup>
const pillars = [
  {
    title: "STEM Pillar",
    desc: `Adapting the STEM Program is a significant step towards aligning with global
    educational trends. As a forward-thinking institution, we are embracing STEM 
    education for its proven effectiveness in preparing students for future challenges 
    and cultivating a culture of innovation and problem-solving.`,
    image: new URL("../assets/images/6.jpeg", import.meta.url).href
  },
  {
    title: "Sports and Talents Pillar",
    desc: `Embracing the Sports and Talents Program is fundamental to our commitment to 
    holistic development. We champion athletic and talent-based pursuits for their 
    role in building discipline, resilience, and teamwork, while unlocking each 
    student's unique potential.`,
    image: new URL("../assets/images/7.jpeg", import.meta.url).href
  },
  {
    title: "Spiritual Wellbeing Pillar",
    desc: `Integrating a Spiritual Wellbeing program is part of our mission to educate 
    the heart and mind. We are intentional about spiritual growth because of its 
    profound impact on fostering inner peace, ethical grounding, and a sense 
    of purpose.`,
    image: new URL("../assets/images/8.jpeg", import.meta.url).href
  },
  {
    title: "Performing Arts Pillar",
    desc: `Adopting a robust Performing Arts curriculum cultivates creative and expressive 
    individuals. We prioritize the arts for their unique ability to develop confidence, 
    empathy, and innovative thinking, preparing students to appreciate and contribute 
    to culture.`,
    image: new URL("../assets/images/9.jpeg", import.meta.url).href
  },
  {
    title: "Digital Literacy Pillar",
    desc: `Implementing a comprehensive Digital Literacy program is essential for navigating 
    the modern world. We are committed to digital fluency to enable responsible, 
    effective, and innovative use of technology.`,
    image: new URL("../assets/images/10.jpeg", import.meta.url).href
  },
  {
    title: "Linkages and Collaboration Pillar",
    desc: `Establishing strong Linkages and Collaboration creates real-world learning 
    opportunities. We actively build partnerships for their immense value in 
    broadening perspectives, enhancing resources, and enabling future success.`,
    image: new URL("../assets/images/11.jpeg", import.meta.url).href
  }
];
</script>

<template>
  <div class="pillar">
    <div class="head">
      <h1>Our Pillars</h1>
    </div>

    <div class="pillar-content">
      <div v-for="(pillar, index) in pillars" :key="index" class="pillar-item">
        <img :src="pillar.image" :alt="pillar.title" class="pillar-image" />
        <div class="pillar-text">
          <h2>{{ pillar.title }}</h2>
          <p>{{ pillar.desc }}</p>
          <button>Learn More</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.pillar {
  display: flex;
  flex-direction: column;
  align-items: center;
  background: #fafafa;
  width: 100%;
}

.head {
  width: 100%;
  background: maroon;
  color: white;
  text-align: center;
  padding: 30px 20px;
}

.head h1 {
  font-size: 2.5rem;
  font-weight: 700;
  margin: 0;
}

.pillar-content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 35px;
  padding: 60px 10%;
  width: 100%;
  box-sizing: border-box;
}

.pillar-item {
  background: white;
  border-radius: 15px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.pillar-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.12);
}

.pillar-image {
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.pillar-text {
  padding: 25px 30px;
}

.pillar-text h2 {
  font-size: 1.6rem;
  color: #222;
  margin-bottom: 15px;
  font-weight: 600;
}

.pillar-text p {
  font-size: 1rem;
  color: #555;
  line-height: 1.7;
}

button {
  background: #1e88e5;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 500;
  margin-top: 15px;
  transition: background 0.3s ease;
}

button:hover {
  background: #1565c0;
}
</style>
