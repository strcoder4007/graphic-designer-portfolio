<template>
  <div class="container">
    <el-row>
      <el-col class="intro-section fade-in">
        <div class="intro-content">
          <div class="intro-text">
            <div class="greetings">Hey there, I'm Riny</div>
            <div class="profile">UI/UX Designer</div>
            <div class="description">I help business grow by crafting amazing web experiences. If you’re looking for a designer that likes to get stuff done, let’s talk.</div>
            <div class="resume-container">
              <el-button class="action-btn" @click="scrollToWork()">
                See my work
                <img src="../../assets/icons/arrow-down.png" alt="Arrow Right Icon" />
              </el-button>
              <el-button class="action-btn" @click="download()">
                Download CV
                <img src="../../assets/icons/download.png" alt="Arrow Right Icon" />
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
    font-size: 59px;
    font-style: normal;
    font-weight: 330;
    line-height: 72px;
    background: var(--brand-gradient, linear-gradient(90deg, #FE572E 0%, #FC3A79 100%));
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }
  .profile {
    color: var(--Black, #261F22);
    text-align: left;
    font-family: Bricolage;
    font-size: 119px;
    font-style: normal;
    font-weight: 700;
    line-height: 144px; /* 121.008% */
    letter-spacing: -3.57px;
  }

  .description {
    color: var(--black75, rgba(38, 31, 34, 0.75));
    text-align: left;
    font-family: Bricolage;
    font-size: 21px;
    font-style: normal;
    font-weight: 400;
    line-height: 30px; /* 142.857% */
    margin-top: 12px;
  }

  .resume-container {
    display: flex;
    flex-direction: row;
    gap: 18px;
    align-items: center;
    padding: 40px 0 0 0;
  }
  .action-btn {
    color: #FFF;
    font-family: Bricolage;
    font-size: 21px;
    font-style: normal;
    font-weight: 700;
    line-height: 30px;
    border-radius: 100px;
    padding: 24px 36px;
    background: var(--brand-gradient, linear-gradient(90deg, #FE572E 0%, #FC3A79 100%));
    box-shadow: 0px 2.76726px 2.21381px 0px rgba(0, 0, 0, 0.02), 0px 6.6501px 5.32008px 0px rgba(0, 0, 0, 0.03), 0px 12.52155px 10.01724px 0px rgba(0, 0, 0, 0.04), 0px 22.33631px 17.86905px 0px rgba(0, 0, 0, 0.04);
    img {
      width: 20px;
      height: 20px;
      margin-left: 15px;
    }
  }
  .hire-btn {
    color: #FFF;
    font-family: Bricolage;
    font-size: 21px;
    font-style: normal;
    font-weight: 700;
    line-height: 30px;
    border-radius: 100px;
    padding: 24px 36px;
    background: linear-gradient(90deg, #FC3A79 0%, #FE572E 100%);
    box-shadow: 0px 2.76726px 2.21381px 0px rgba(0, 0, 0, 0.02), 0px 6.6501px 5.32008px 0px rgba(0, 0, 0, 0.03), 0px 12.52155px 10.01724px 0px rgba(0, 0, 0, 0.04), 0px 22.33631px 17.86905px 0px rgba(0, 0, 0, 0.04);
    display: flex;
    align-items: center;
    gap: 10px;
    transition: background 0.3s;
    img {
      width: 22px;
      height: 22px;
      margin-left: 10px;
    }
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
    img {
      width: 320px;
      max-width: 100%;
      border-radius: 24px;
      box-shadow: 0 8px 32px rgba(252, 58, 121, 0.12);
      object-fit: cover;
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
    }
    .intro-text {
      align-items: center;
      text-align: center;
    }
    .greetings {
      font-weight: 400;
      font-size: 30px;
      text-align: center;
    }
    .profile {
      font-size: 50px;
      line-height: 60px;
      text-align: center;
    }

    .description {
      font-size: 15px;
      line-height: 20px;
      padding: 0 20px;
      margin-top: 20px;
      text-align: center;
    }

    .resume-container {
      flex-direction: column;
      gap: 12px;
      padding: 24px 0 0 0;
    }
    .action-btn, .hire-btn {
      font-size: 15px;
      line-height: 20px;
      padding: 20px 25px;
      img {
        width: 15px;
        height: 15px;
        margin-left: 10px;
      }
    }
    .intro-image {
      img {
        width: 180px;
        border-radius: 16px;
      }
    }
  }
}
</style>
