<script setup>
</script>

<template>
  <div class="mission-page">
    <header class="header">
      <h1>Precious School</h1>
      <p>Mission, Vision & Core Values</p>
    </header>

    <section class="mission">
      <h2>Our Mission</h2>
      <p>
        To holistically educate and empower the boychild by providing a transformative learning
        environment that cultivates academic excellence, nurtures unique talents, and instills robust
        life skills. We are dedicated to developing purpose-driven, innovative, and globally-minded
        young men of strong character, prepared to lead and serve in a dynamic world.
      </p>
    </section>

    <section class="vision">
      <h2>Our Vision</h2>
      <p>
        To be the leading global educational institution that redefines excellence for the boychild,
        creating a generation of leaders, innovators, and ethical citizens who are rooted in strong
        values and equipped to make a positive impact in their communities and beyond.
      </p>
    </section>

    <section class="core-values">
      <h2>Our Core Values</h2>
      <ul>
        <li>
          <strong>Excellence with Purpose:</strong> We strive for the highest standards in all we do,
          not for the sake of achievement alone, but with clear intention and a drive to make a
          meaningful difference.
        </li>
        <li>
          <strong>Integrity and Character:</strong> We build our community on a foundation of
          unwavering honesty, respect, and moral courage. We believe that strong character is the
          cornerstone of true leadership.
        </li>
        <li>
          <strong>Innovation and Creativity:</strong> We foster a culture of curiosity, critical
          thinking, and creative problem-solving. We encourage our students to challenge conventions
          and imagine new possibilities.
        </li>
        <li>
          <strong>Global Mindedness with Local Roots:</strong> We celebrate our Kenyan heritage while
          embracing diverse cultures and global perspectives. We prepare our students to engage with
          the world as informed and compassionate citizens.
        </li>
        <li>
          <strong>Holistic Growth:</strong> We are committed to the balanced development of every
          student—mind, body, and spirit—through academics, arts, sports, and emotional well-being.
        </li>
        <li>
          <strong>Sustainable Stewardship:</strong> We act as responsible custodians of our
          environment and community, teaching our students to lead with sustainability and social
          responsibility at the forefront.
        </li>
        <li>
          <strong>Resilient Community:</strong> We cultivate a supportive and inclusive brotherhood
          where students learn resilience, collaboration, and the importance of lifting each other up.
        </li>
      </ul>
    </section>

    <section class="pillars">
      <h2>The Four Pillars of a Precious Education</h2>
      <div class="pillars-grid">
        <div class="pillar">
          <h3>Academic Rigor</h3>
          <p>
            A challenging and engaging curriculum that inspires a lifelong love of learning and
            intellectual discovery.
          </p>
        </div>
        <div class="pillar">
          <h3>Talent Development</h3>
          <p>
            A commitment to identifying, nurturing, and celebrating the unique gifts and passions of
            every student.
          </p>
        </div>
        <div class="pillar">
          <h3>Life Skills Mastery</h3>
          <p>
            Practical learning in leadership, communication, and critical thinking to navigate the
            complexities of adult life with confidence.
          </p>
        </div>
        <div class="pillar">
          <h3>Global Citizenship</h3>
          <p>
            An education that develops cultural awareness, ethical reasoning, and a sense of
            responsibility to the wider world.
          </p>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
.mission-page {
  font-family: "Poppins", sans-serif;
  color: #222;
  background: linear-gradient(to bottom right, #f8fafc, #eef2f7);
  padding: 60px 10%;
  line-height: 1.8;
}

.header {
  text-align: center;
  margin-bottom: 50px;
}

.header h1 {
  font-size: 2.8rem;
  color: maroon;
  margin-bottom: 0.3rem;
}

.header p {
  font-size: 1.2rem;
  color: #526480;
  letter-spacing: 1px;
}

section {
  margin-bottom: 50px;
  background: white;
  padding: 30px;
  border-radius: 16px;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease;
}

section:hover {
  transform: translateY(-4px);
}

h2 {
  color: maroon;
  border-left: 5px solid maroon;
  padding-left: 12px;
  margin-bottom: 20px;
}

p {
  font-size: 1rem;
  color: #333;
}

ul {
  list-style: none;
  padding: 0;
}

ul li {
  margin-bottom: 18px;
  padding-left: 1.5rem;
  position: relative;
}

ul li::before {
  content: "•";
  color: maroon;
  font-weight: bold;
  position: absolute;
  left: 0;
}

.pillars-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
  gap: 25px;
}

.pillar {
  background: #f5f8ff;
  padding: 20px;
  border-radius: 12px;
  border: 1px solid #e2e8f0;
  transition: all 0.3s ease;
}

.pillar:hover {
  background: #eaf1ff;
  transform: scale(1.03);
}

.pillar h3 {
  color: maroon;
  font-size: 1.2rem;
  margin-bottom: 10px;
}
</style>
