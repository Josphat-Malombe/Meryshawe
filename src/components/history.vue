<script setup>
</script>

<template>
  <div class="history">
    <div class="title">
      <h1>The History of Precious School: A Legacy of Nurturing Tomorrow's Leaders</h1>
    </div>

    <div class="content">
      <section>
        <h2>Chapter 1: A Vision Takes Root (2000–2005)</h2>
        <p>
          Precious School first opened its gates in January 2000 on a modest, leased plot on the outskirts of Nairobi.
          It was founded by Dr. Anisa Okeke and Mr. Samuel Githinji, two visionary educators who saw a critical gap
          in the educational landscape. Their dream was simple yet profound: to create a school that would do more than
          just impart academic knowledge. They envisioned a sanctuary where the boychild could be holistically nurtured—
          intellectually, socially, and ethically—to become a purposeful and creative man of character.
        </p>
        <p>
          The school began with just 47 students and a handful of dedicated teachers. From the outset, the "Precious Ethos"
          was established, built on four core pillars: Academic Rigor, Talent Development, Life Skills, and Global Citizenship.
          The early years were focused on building a strong, familial community where these values could flourish.
        </p>
      </section>

      <section>
        <h2>Chapter 2: Building the Foundation (2006–2015)</h2>
        <p>
          As the school's reputation for excellence and character development grew, so did its population. By 2008,
          Precious School had outgrown its original home. A pivotal moment came with the acquisition of land in the newly
          planned Konza Technopolis. This decision was a bold statement of intent, aligning the school's future with Kenya's
          vision for a technologically advanced and innovative future.
        </p>
        <p>
          The decade was marked by consistent achievement. Our students began to excel not only in national examinations
          but also in drama, music, sports, and debate. The school's commitment to sustainability began with student-led
          projects in rainwater harvesting and tree planting, laying the groundwork for the eco-conscious campus we have today.
        </p>
      </section>

      <section>
        <h2>Chapter 3: The Konza Era Begins (2016–2022)</h2>
        <p>
          In 2019, the school community moved to its permanent, state-of-the-art campus in Konza. This was a transformative period.
          The new campus was more than just buildings; it was the physical embodiment of our philosophy. Inspired by the communal
          layout of the traditional Manyatta but reimagined for a digital age, the architecture itself became a tool for learning.
        </p>
        <p>
          The move to Konza allowed for the introduction of advanced programs in coding, robotics, and entrepreneurship. Our partnership
          with tech firms within the technopolis provided students with unparalleled exposure, making the school a benchmark for innovative
          education in Kenya. It was during this time that Precious School truly cemented its identity as a global school with a local heart.
        </p>
      </section>

      <section>
        <h2>Chapter 4: A Legacy Secured, A Future Embraced (2023 and Beyond)</h2>
        <p>
          Today, Precious School stands as a testament to its founders' vision. From a small cohort of 47, we have grown into a vibrant community
          of over 1,200 students, yet we have vigilantly preserved our close-knit, nurturing spirit.
        </p>
        <p>
          Our history is not just in our milestones, but in the stories of our alumni—engineers, artists, entrepreneurs, and community leaders—who are
          making a difference around the world, guided by the purpose-driven foundation they received here.
        </p>
        <p>
          As we look to the future, Precious School remains committed to its core mission while continuously evolving. We are dedicated to empowering
          each new generation of young men to be creative, innovative, and global-minded, ready to conquer the challenges and opportunities of a dynamic world.
        </p>
      </section>
    </div>
  </div>
</template>

<style scoped>
.history {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  background: #fafafa;
  color: #222;
  font-family: "Poppins", system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
  margin: 10px;
}

.title {
  width: 100%;
  background: linear-gradient(90deg, #6d0000, #8b1f1f);
  box-sizing: border-box;
  display: flex;
  justify-content: center;
  align-items: center;
  padding:70px;
  padding-bottom: 15px;
}

.title h1 {
  color: #fff;
  font-size: 1.25rem;
  max-width: 1200px;
  margin: 0;
  text-align: center;
  line-height: 1.2;
  font-weight: 700;
}

.content {
  width: 100%;
  max-width: 1100px;
  padding: 48px 6%;
  box-sizing: border-box;
  background: transparent;
}

.content section {
  margin-bottom: 32px;
}

.content h2 {
  color: #6d0000;
  font-size: 1.25rem;
  margin: 0 0 12px 0;
  font-weight: 700;
}

.content p {
  color: #333;
  font-size: 1rem;
  line-height: 1.75;
  margin: 0 0 14px 0;
  text-align: justify;
}

@media (min-width: 1200px) {
  .title h1 {
    font-size: 2.4rem;
  }
  .content p {
    font-size: 1.05rem;
  }
}

@media (max-width: 900px) {
  .title {
    padding: 80px ;
  }
  .title h1 {
    font-size: 1.25rem;
  }
  .content {
    padding: 24px 5%;
  }
  .content h2 {
    font-size: 1.05rem;
  }
  .content p {
    font-size: 0.98rem;
  }
}
</style>
