<template>
  <section class="about-hero">
    <div class="about-hero-content">
      <div class="about-hero-text">
        <h1 class="about-title">
          <span>Riny Yadav</span>
          <span class="about-role">AI Graphic Designer & Creative Technologist</span>
        </h1>
        <p class="about-summary">
          With two years of professional experience, I bring a passion for visual storytelling and a fascination with the impact of design on people’s lives. My journey began with a love for creativity and technology, leading me to blend traditional graphic design with advanced AI—crafting everything from classic branding to AI-generated interfaces, images, videos, and avatars.
        </p>
      </div>
      <div class="about-hero-image">
        <div class="about-image-container">
          <img src="../assets/portrait/one.png" alt="Riny Yadav Portrait" />
        </div>
      </div>
    </div>
  </section>

  <section class="about-expertise">
    <div class="expertise-block">
      <img src="../assets/icons/quality.svg" alt="Design Icon" />
      <div>
        <h2>Traditional Graphic Design</h2>
        <p>
          Expert in branding, illustration, print, and digital design. I craft timeless visuals and user experiences rooted in design fundamentals.
        </p>
      </div>
    </div>
    <div class="expertise-block">
      <img src="../assets/icons/rocket.svg" alt="AI Icon" />
      <div>
        <h2>AI-Driven Creation & Prompting</h2>
        <p>
          I generate unique interfaces, images, videos, and avatars using advanced AI tools and creative prompting—delivering innovative solutions at speed and scale.
        </p>
      </div>
    </div>
  </section>

  <section class="about-process">
    <h2 class="process-title">How I Work</h2>
    <div class="process-steps">
      <div class="process-step">
        <img src="../assets/icons/brand-icon.png" alt="Discovery" />
        <span>Discovery & Strategy</span>
      </div>
      <div class="process-step">
        <img src="../assets/icons/quality.svg" alt="Design" />
        <span>Design & Prototyping</span>
      </div>
      <div class="process-step">
        <img src="../assets/icons/rocket.svg" alt="AI Generation" />
        <span>AI Generation, Prompting & Iteration</span>
      </div>
      <div class="process-step">
        <img src="../assets/icons/phone.svg" alt="Delivery" />
        <span>Delivery & Support</span>
      </div>
    </div>
  </section>

  <section class="about-cta">
    <h2>Ready to create something extraordinary?</h2>
    <p>
      Let’s combine the best of human creativity and AI to bring your vision to life.
    </p>
    <el-button class="about-contact-btn" @click="$router.push({ name: 'Contact' })">
      Contact Me
    </el-button>
  </section>

  <ToolsSection />
  <FreelanceSection class="freelance-section" />
  <FooterSection />
</template>

<script>
import FooterSection from './sections/FooterSection.vue';
import ToolsSection from './sections/ToolsSection.vue';
import FreelanceSection from './sections/FreelanceSection.vue';

export default {
  name: "AboutPage",
  components: {
    FreelanceSection,
    FooterSection,
    ToolsSection
  }
};
</script>

<style lang="scss" scoped>
.about-hero {
  width: 100%;
  background: none;
  padding: 80px 0 40px 0;
  display: flex;
  justify-content: center;
  align-items: center;
}
.about-hero-content {
  display: flex;
  flex-direction: row;
  align-items: center;
  max-width: 1200px;
  width: 100%;
  gap: 64px;
  padding: 0 32px;
}
.about-hero-text {
  flex: 2;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  text-align: left;
}
.about-title {
  font-family: 'Neue Montreal', 'Brandon', Arial, sans-serif;
  font-size: 3.2rem;
  font-weight: 700;
  line-height: 1.1;
  margin-bottom: 18px;
  background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  span.about-role {
    display: block;
    font-size: 1.3rem;
    font-weight: 400;
    color: #261F22;
    background: none;
    -webkit-text-fill-color: initial;
    margin-top: 8px;
    letter-spacing: 0.5px;
  }
}
.about-summary {
  font-family: 'Neue Montreal', 'Bricolage', Arial, sans-serif;
  font-size: 1.25rem;
  color: #261F22;
  margin-bottom: 0;
  margin-top: 0;
  max-width: 600px;
  line-height: 1.6;
}
.about-hero-image {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  .about-image-container {
    width: 260px;
    height: 260px;
    min-width: 180px;
    min-height: 180px;
    max-width: 320px;
    max-height: 320px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #fff;
    border-radius: 32px;
    overflow: hidden;
    box-shadow: 0 12px 48px 0px rgba(252, 58, 121, 0.18), 0 8px 32px rgba(0,0,0,0.10);
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      border-radius: 0;
      display: block;
    }
  }
}

.about-expertise {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: stretch;
  gap: 48px;
  margin: 64px auto 32px auto;
  max-width: 1100px;
  width: 100%;
  background: linear-gradient(120deg, #fff6f0 0%, #ffe0e6 100%);
  border-radius: 32px;
  padding: 48px 32px;
  box-shadow: 0 4px 32px 0px rgba(252, 58, 121, 0.07);
  .expertise-block {
    flex: 1;
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    gap: 24px;
    background: none;
    padding: 0;
    img {
      width: 54px;
      height: 54px;
      margin-top: 4px;
    }
    h2 {
      font-family: 'Neue Montreal', 'Brandon', Arial, sans-serif;
      font-size: 1.5rem;
      font-weight: 700;
      margin-bottom: 8px;
      color: #FE572E;
      background: none;
    }
    p {
      font-family: 'Neue Montreal', 'Bricolage', Arial, sans-serif;
      font-size: 1.08rem;
      color: #261F22;
      margin: 0;
      line-height: 1.6;
    }
  }
}

.about-process {
  width: 100%;
  background: linear-gradient(90deg, #fff6f0 0%, #ffe0e6 100%);
  padding: 56px 0 40px 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  .process-title {
    font-family: 'Neue Montreal', 'Brandon', Arial, sans-serif;
    font-size: 2rem;
    font-weight: 700;
    margin-bottom: 32px;
    background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }
  .process-steps {
    display: flex;
    flex-direction: row;
    gap: 48px;
    justify-content: center;
    align-items: flex-start;
    width: 100%;
    max-width: 900px;
    .process-step {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 12px;
      img {
        width: 48px;
        height: 48px;
        margin-bottom: 8px;
      }
      span {
        font-family: 'Neue Montreal', 'Bricolage', Arial, sans-serif;
        font-size: 1.08rem;
        color: #261F22;
        text-align: center;
      }
    }
  }
}

.about-cta {
  width: 100%;
  padding: 56px 0 32px 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  background: none;
  h2 {
    font-family: 'Neue Montreal', 'Brandon', Arial, sans-serif;
    font-size: 2.1rem;
    font-weight: 700;
    color: #FE572E;
    margin-bottom: 12px;
    text-align: center;
  }
  p {
    font-family: 'Neue Montreal', 'Bricolage', Arial, sans-serif;
    font-size: 1.1rem;
    color: #261F22;
    margin-bottom: 24px;
    text-align: center;
  }
  .about-contact-btn {
    font-family: 'Neue Montreal', 'Brandon', Arial, sans-serif;
    font-size: 1.1rem;
    font-weight: 600;
    padding: 18px 44px;
    border-radius: 100px;
    background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
    color: #fff;
    border: none;
    box-shadow: 0 4px 16px rgba(252, 58, 121, 0.13);
    transition: background 0.22s, color 0.22s, box-shadow 0.22s, transform 0.18s;
    cursor: pointer;
    &:hover {
      background: linear-gradient(90deg, #FC3A79 0%, #FE572E 100%);
      color: #fff;
      transform: translateY(-2px) scale(1.04);
    }
  }
}

@media (max-width: 900px) {
  .about-hero-content {
    flex-direction: column;
    gap: 32px;
    align-items: center;
    text-align: center;
  }
  .about-hero-text {
    align-items: center;
    text-align: center;
  }
  .about-hero-image .about-image-container {
    width: 180px;
    height: 180px;
    border-radius: 20px;
  }
  .about-expertise {
    flex-direction: column;
    gap: 32px;
    padding: 32px 12px;
    .expertise-block {
      flex-direction: row;
      align-items: flex-start;
      gap: 18px;
      img {
        width: 40px;
        height: 40px;
      }
      h2 {
        font-size: 1.2rem;
      }
      p {
        font-size: 0.98rem;
      }
    }
  }
  .about-process .process-steps {
    flex-direction: column;
    gap: 24px;
    align-items: center;
  }
}

@media (max-width: 600px) {
  .about-hero {
    padding: 36px 0 18px 0;
  }
  .about-title {
    font-size: 2rem;
    span.about-role {
      font-size: 1rem;
    }
  }
  .about-summary {
    font-size: 0.98rem;
  }
  .about-hero-image .about-image-container {
    width: 120px;
    height: 120px;
    border-radius: 12px;
  }
  .about-expertise {
    gap: 18px;
    padding: 18px 4px;
    .expertise-block {
      gap: 10px;
      img {
        width: 28px;
        height: 28px;
      }
      h2 {
        font-size: 1rem;
      }
      p {
        font-size: 0.88rem;
      }
    }
  }
  .about-process {
    padding: 24px 0 18px 0;
    .process-title {
      font-size: 1.1rem;
    }
    .process-steps .process-step img {
      width: 28px;
      height: 28px;
    }
    .process-steps .process-step span {
      font-size: 0.88rem;
    }
  }
  .about-cta {
    padding: 24px 0 12px 0;
    h2 {
      font-size: 1.1rem;
    }
    p, .about-contact-btn {
      font-size: 0.98rem;
      padding: 12px 24px;
    }
  }
}
</style>
