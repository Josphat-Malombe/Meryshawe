<script>
export default {};
</script>

<template>
  <div class="gallery-page">
    <!-- Left: Gallery Section -->
    <div class="left">
      <h1>School Gallery</h1>
      <div class="buttons">
        <button class="photo-btn">Photos</button>
        <button class="video-btn">Videos</button>
      </div>
    </div>

    <!-- Right: Architecture Section -->
    <div class="right">
      <h1>PRECIOUS SCHOOL ARCHITECTURAL CONCEPT</h1>
      <div class="content">
        <p>
          Nestled within the innovative landscape of Konza Technopolis, Precious School presents a forward-thinking architectural vision that harmonizes the 
          timeless wisdom of African design with the dynamic pulse of a technology hub. The campus is conceptually inspired by the Maa homestead—the 
          Manyatta—reinterpreting its protective, community-centric layout for the 21st-century boychild. This design philosophy places the student at the epicenter
          of a nurturing environment, surrounded by layers of security, inspiration, and community.
        </p>

        <p>
          A Campus for Dynamic Growth and Mindful Transition Embodying the spirit of both pastoral movement and technological flow, the campus is designed to 
          prevent monotony and stimulate continuous growth. Expansive, multi-dimensional spaces encourage physical movement and mental shifts between activities. 
          Deliberate buffers between academic, creative, athletic, and social zones allow students to transition mindfully from one mindset to the next.
        </p>

        <p>
          A Living Laboratory of Sustainable Innovation
          Precious School is a testament to its values, where the campus itself is the primary teacher of sustainability and global citizenship.
        </p>

        <p>
          Intelligent Environmental Design: Building orientation and intelligent shading ensure optimal natural lighting and passive ventilation, eliminating the need for artificial lighting 
          during daytime hours. Integrated Resource Cycles: A state-of-the-art rainwater harvesting system, a significant on-site solar power array, 
          and a closed-loop wastewater treatment plant demonstrate practical circular economies in action.
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.gallery-page {
  display: flex;
  flex-direction: row;
  width: 100%;
  min-height: 100vh; /* allows full screen but page scrolls naturally */
  font-family: "Poppins", sans-serif;
  overflow: visible; /* no hidden content */
  margin: 0;
}

/* Left Section (Gallery) */
.left {
  flex: 1;
  background: linear-gradient(to bottom right, #ffffff, #434141);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 40px;
}

.left h1 {
  font-size: 2.5rem;
  color: #6d0000;
  margin-bottom: 30px;
  letter-spacing: 1px;
}

.buttons {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

button {
  padding: 14px 30px;
  border: none;
  font-size: 1rem;
  border-radius: 25px;
  cursor: pointer;
  font-weight: 600;
  transition: all 0.3s ease;
  width: 180px;
}

.photo-btn {
  background-color: #6d0000;
  color: white;
}

.photo-btn:hover {
  background-color: #8b0000;
}

.video-btn {
  background-color: transparent;
  border: 2px solid #6d0000;
  color: #6d0000;
}

.video-btn:hover {
  background-color: #6d0000;
  color: white;
}

/* Right Section (Architecture) */
.right {
  flex: 1.5;
  background-color: #6d0000;
  color: white;
  padding: 60px 50px;
  overflow: hidden; /* prevents internal scroll */
  position: relative;
}

.right h1 {
  font-size: 2rem;
  margin-bottom: 20px;
  border-bottom: 2px solid white;
  padding-bottom: 10px;
}

.right .content {
  overflow: visible;
  max-height: none;
}

.right p {
  line-height: 1.7;
  font-size: 1.05rem;
  margin-bottom: 20px;
}

/* Responsive Design */
@media (max-width: 900px) {
  .gallery-page {
    flex-direction: column;
  }

  .right {
    padding: 40px 20px;
  }
}
</style>
