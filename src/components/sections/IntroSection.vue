<template>
  <div class="container">
    <el-row>
      <el-col class="intro-section fade-in">
        <div class="intro-content">
          <div class="intro-text">
            <div class="greetings">Hi! I'm Riny</div>
            <div class="profile">AI-Powered UI/UX & Visual Designer</div>
            <div class="description">
              I leverage advanced AI to deliver creative, high-quality graphics and interfaces—combining human insight with machine precision for results that stand out.
            </div>
            <div class="resume-container">
              <el-button class="action-btn" @click="scrollToWork()">
                Explore Work
                <img src="../../assets/icons/arrow-down.png" alt="Arrow Right Icon" />
              </el-button>
              <el-button class="action-btn" @click="download()">
                Download Resume
                <img src="../../assets/icons/download.png" alt="Download Icon" />
              </el-button>
              <el-button class="hire-btn" @click="hireMe()">
                Hire Me
                <img src="../../assets/icons/rocket.svg" alt="Hire Me Icon" />
              </el-button>
            </div>
          </div>
          <div class="intro-image">
            <img src="../../assets/portrait/one.png" alt="Riny Portrait" />
          </div>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
// import { ref } from 'vue';

export default {
  setup() {

    return {
    };
  },
  methods: {
    scrollToWork() {
      document.getElementById('work-section').scrollIntoView()
    },
    download() {
      const link = document.createElement('a')
      link.href = 'https://strcoder4007.github.io/graphic-designer-portfolio/resume.pdf'
      link.download = 'Riny_Resume.pdf'
      link.click();
    },
    hireMe() {
      // Scroll to contact section or open mail
      const contact = document.getElementById('contact-section');
      if (contact) {
        contact.scrollIntoView({ behavior: 'smooth' });
      } else {
        window.open('mailto:your.email@example.com?subject=Hiring Inquiry for Riny', '_blank');
      }
    }
  }
};
</script>

<style lang="scss" scoped>

.container {
  background: transparent;
}
.intro-section {
  height: calc(100vh - 100px);
  background: transparent;
  backdrop-filter: blur(2px);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  animation: fadeIn 1.2s ease-in;

  .intro-content {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    width: 100%;
    max-width: 1100px;
    gap: 48px;
    margin: 0 auto;
  }
  .intro-text {
    flex: 1;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: center;
    min-width: 0;
  }
  .greetings {
    text-align: left;
    font-family: Brandon;
    font-size: 32px;
    font-style: normal;
    font-weight: 400;
    line-height: 40px;
    background: var(--brand-gradient, linear-gradient(90deg, #FE572E 0%, #FC3A79 100%));
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }
  .profile {
    color: var(--Black, #261F22);
    text-align: left;
    font-family: Bricolage;
    font-size: 78px;
    font-style: normal;
    font-weight: 700;
    line-height: 78px;
    letter-spacing: -1.2px;
  }

  .description {
    color: var(--black75, rgba(38, 31, 34, 0.75));
    text-align: left;
    font-family: Bricolage;
    font-size: 15px;
    font-style: normal;
    font-weight: 400;
    line-height: 22px;
    margin-top: 12px;
  }

  .resume-container {
    display: flex;
    flex-direction: row;
    gap: 18px;
    align-items: center;
    padding: 32px 0 0 0;
  }
  .action-btn {
    color: #FFF;
    font-family: Bricolage;
    font-size: 18px;
    font-style: normal;
    font-weight: 700;
    line-height: 32px;
    border-radius: 100px;
    padding: 28px 48px;
    background: var(--brand-gradient, linear-gradient(90deg, #FE572E 0%, #FC3A79 100%));
    box-shadow: 0px 4px 16px 0px rgba(252, 58, 121, 0.18), 0px 2.76726px 2.21381px 0px rgba(0, 0, 0, 0.02);
    img {
      width: 20px;
      height: 20px;
      margin-left: 12px;
    }
  }
  .hire-btn {
    color: #FFF;
    font-family: Bricolage;
    font-size: 18px;
    font-style: normal;
    font-weight: 700;
    line-height: 32px;
    border-radius: 100px;
    padding: 28px 48px;
    background: linear-gradient(90deg, #FC3A79 0%, #FE572E 100%);
    box-shadow: 0px 4px 16px 0px rgba(252, 58, 121, 0.18), 0px 2.76726px 2.21381px 0px rgba(0, 0, 0, 0.02);
    display: flex;
    align-items: center;
    gap: 12px;
    transition: background 0.3s;
    img {
      width: 22px;
      height: 22px;
      margin-left: 10px;
    }
  }
  .hire-btn img {
    filter: brightness(0) invert(1);
  }
  .hire-btn:hover {
    background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
  }
  .intro-image {
    flex: 1;
    display: flex;
    align-items: center;
    justify-content: center;
    min-width: 0;
    height: 100%;
    margin-top: -32px;
    img {
      width: 320px;
      max-width: 100%;
      max-height: 320px;
      aspect-ratio: 1/1;
      border-radius: 24px;
      box-shadow: 0 12px 48px 0px rgba(252, 58, 121, 0.28), 0 8px 32px rgba(0,0,0,0.10);
      object-fit: cover;
      display: block;
      margin: auto;
    }
  }
}

.fade-in {
  animation: fadeIn 1.2s ease-in;
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(40px);}
  to { opacity: 1; transform: translateY(0);}
}
@media (max-width: 768px) {
  .intro-section {
    height: 70vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    .intro-content {
      flex-direction: column;
      gap: 24px;
      align-items: center;
      justify-content: center;
      margin: 0 auto;
    }
    .intro-text {
      align-items: center;
      text-align: center;
    }
    .greetings {
      font-weight: 400;
      font-size: 18px;
      text-align: center;
      margin-bottom: 6px;
    }
    .profile {
      font-size: 28px;
      line-height: 34px;
      text-align: center;
      margin-bottom: 10px;
    }

    .description {
      font-size: 13px;
      line-height: 18px;
      padding: 0 10px;
      margin-top: 14px;
      text-align: center;
    }

    .resume-container {
      flex-direction: column;
      gap: 12px;
      padding: 24px 0 0 0;
      margin-top: 32px;
    }
    .action-btn, .hire-btn {
      font-size: 18px;
      line-height: 28px;
      padding: 22px 36px;
      img {
        width: 20px;
        height: 20px;
        margin-left: 10px;
      }
    }
    .hire-btn img {
      filter: brightness(0) invert(1);
    }
    .intro-image {
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-top: -18px;
      img {
        width: 140px;
        max-width: 100%;
        max-height: 140px;
        aspect-ratio: 1/1;
        border-radius: 16px;
        margin: auto;
        display: block;
        object-fit: cover;
      }
    }
  }
}
</style>
