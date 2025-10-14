<script setup>
</script>

<template>
  <div class="us">
    <div class="head">
      <h1>About Us</h1>
    </div>

    <div class="us-content">
      <div class="us-text">
        <h2>Who We Are</h2>
        <p>
          Precious School is a dedicated learning community where boys grow into capable, confident young men. We provide a holistic education that 
          champions academic excellence while equally nurturing social intelligence, individual talents, and critical life skills.
          <br><br>
          Serving families from our local community and around the world, we offer an education that blends global perspectives with strong values.
          Our environment is specifically designed to support, challenge, and empower the boychild for the complexities of the modern world.
          <br><br>
          Our entire ecosystem—from our purpose-built facilities and innovative curriculum to our exceptional educators and success metrics—is designed with one goal: 
          to develop purpose-driven, creative, and innovative global citizens.
          <br><br>
          At the heart of Precious School is a deep respect for diversity, where we actively learn from and celebrate a multitude of cultures and religions.
        </p>
      </div>

      <div class="virtual">
        <h2>Virtual Tour</h2>
        <div class="video-wrapper">
          <iframe
            width="560"
            height="315"
            src="https://www.youtube.com/embed/fZS22EY5-b4?si=3LbwIroYwzepRU1e"
            title="Virtual Tour"
            frameborder="0"
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
          ></iframe>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.us {
  display: flex;
  flex-direction: column;
  align-items: center;
  background: url("../assets/images/1.jpeg") no-repeat center center/cover;
  position: relative;
  width: 100%;
  color: #fff;
  overflow: hidden;
}

/* Dark overlay for better text contrast */
.us::before {
  content: "";
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.55);
  z-index: 0;
}

.head {
  width: 100%;
  background: maroon;
  color: white;
  text-align: center;
  padding: 30px 20px;
  position: relative;
  z-index: 1;
}

.head h1 {
  font-size: 2.5rem;
  font-weight: 700;
  margin: 0;
}

.us-content {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 40px;
  padding: 60px 8%;
  position: relative;
  z-index: 1;
  flex-wrap: wrap;
}

.us-text {
  flex: 1;
  min-width: 300px;
  color: #f0f0f0;
  background: rgba(0, 0, 0, 0.4);
  padding: 25px 30px;
  border-radius: 10px;
  line-height: 1.8;
}

.us-text h2 {
  font-size: 1.8rem;
  color: #ffcc00;
  margin-bottom: 15px;
}

.us-text p {
  font-size: 1rem;
  color: #f1f1f1;
}

.virtual {
  flex: 1;
  min-width: 300px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.virtual h2 {
  font-size: 1.8rem;
  color: #ffcc00;
  margin-bottom: 20px;
}

.video-wrapper {
  position: relative;
  width: 100%;
  max-width: 560px;
  aspect-ratio: 16/9;
  overflow: hidden;
  border-radius: 10px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.5);
}

.video-wrapper iframe {
  width: 100%;
  height: 100%;
  border: none;
}

/* Responsive Design */
@media (max-width: 900px) {
  .us-content {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .us-text, .virtual {
    width: 100%;
  }

  .us-text {
    margin-bottom: 30px;
  }
}
</style>
