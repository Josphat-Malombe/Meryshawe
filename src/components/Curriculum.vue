<script></script>

<template>
  <div class="curriculum">
    <div class="curriculum-content">
      <h1>Our Curriculum</h1>

      <p>
        As a leading high school in Kenya, we proudly offer a dynamic learning environment that
        provides both the time-tested 8.4.4 curriculum and the forward-thinking Competency-Based
        Education (CBE).<br /><br />
        Our commitment to excellence is reflected in our holistic approach, nurturing students to
        thrive academically, socially, and personally. The 8.4.4 curriculum provides a solid
        foundation with a rigorous academic structure, while the CBE empowers learners with
        essential life skills, critical thinking, and creativity.
      </p>
    </div>
    <div class="curriculum-section">
  <div class="eight">
    <div class="icon">
      <!-- Book/Graduation Cap SVG for 8-4-4 -->
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor">
        <path d="M12 2 1 7l11 5 9-4.09V17h2V7L12 2z"/>
        <path d="M11 12.75 3.5 9.11V17a2 2 0 0 0 2 2h6.5v-6.25z"/>
        <path d="M13 12.75V19.5h6.5a2 2 0 0 0 2-2v-8.39L13 12.75z"/>
      </svg>
    </div>
    <h1>The 8-4-4 Curriculum</h1>
    <p>
      Precious School is a beacon of academic excellence. We offer the 8-4-4 system,
      delivering an education that goes beyond textbooks to sculpt students into future leaders.
    </p>
    <button>Learn More</button>
  </div>

  <div class="cbe">
    <div class="icon">
      <!-- Innovation / Skill Development SVG for CBE -->
      <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 24 24">
        <path d="M12 2a5 5 0 0 0-5 5v4H6a2 2 0 0 0-2 2v5h16v-5a2 2 0 0 0-2-2h-1V7a5 5 0 0 0-5-5z"/>
        <path d="M8 21h8a1 1 0 0 1 0 2H8a1 1 0 1 1 0-2z"/>
      </svg>
    </div>
    <h1>CBE</h1>
    <p>
      Our Competency-Based Education (CBE) program is designed to equip students with the skills 
      and knowledge needed to excel in the modern world. Through personalized learning paths, 
      practical applications, and real-world experiences, we prepare our students to be adaptable, 
      innovative, and ready to tackle future challenges with confidence.
    </p>
    <button>Learn More</button>
  </div>
</div>

  </div>
</template>

<style scoped>
.curriculum {
  width: 100%;
  padding: 4rem 0;
  background-color: white;
  margin: 0;
}

.curriculum-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  text-align: left;
}

.curriculum h1 {
  font-size: 2rem;
  margin-bottom: 2rem;
  color: maroon;
  text-align: center;
  font-weight: 500;
}

.curriculum p {
  line-height: 1.8;
  color: #333;
  font-size: 1.1rem;
  margin: 0 auto;
  max-width: 900px;
}
.curriculum-section {
  display: flex;
  flex-wrap: wrap;
  gap: 40px;
  padding: 40px 10%;
  justify-content: center;
  
}

.curriculum-section div {
  flex: 1 1 45%;
  background: #f9f9f9;
  border-radius: 20px;
  padding: 30px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, background 0.3s ease;
}

.curriculum-section div:hover {
  transform: translateY(-5px);
  background: #ffffff;
}

.icon {
  width: 60px;
  height: 60px;
  color: #1e88e5;
  margin-bottom: 20px;
}

.icon svg {
  width: 100%;
  height: 100%;
}

button {
  background: #1e88e5;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 8px;
  cursor: pointer;
  margin-top: 15px;
  transition: background 0.3s ease;
}

button:hover {
  background: #1565c0;
}

</style>
