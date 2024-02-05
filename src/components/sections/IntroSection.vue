<template>
  <div class="container">
    <el-row>
      <el-col class="intro-section">
        <div class="greetings">Hey there, I'm Riny</div>
        <div class="profile">UI/UX Designer</div>
        <div class="description">I help business grow by crafting amazing web experiences. If you’re looking for a designer that likes to get stuff done, let’s talk.</div>

        <div class="resume-container">
          <el-button class="action-btn" @click="scrollToWork()">
            See my work
            <img src="../../assets/icons/arrow-down.png" alt="Arrow Right Icon" />
          </el-button>
          <el-button class="action-btn">
            Download CV
            <img src="../../assets/icons/download.png" alt="Arrow Right Icon" />
          </el-button>
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

  .greetings {
    text-align: center;
    font-family: Brandon;
    font-size: 59px;
    font-style: normal;
    font-weight: 330;
    line-height: 72px; /* 122.034% */
    letter-spacing: -1.77px;
    background: var(--brand-gradient, linear-gradient(90deg, #FE572E 0%, #FC3A79 100%));
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }
  .profile {
    color: var(--Black, #261F22);
    text-align: center;
    font-family: Bricolage;
    font-size: 119px;
    font-style: normal;
    font-weight: 700;
    line-height: 144px; /* 121.008% */
    letter-spacing: -3.57px;
  }

  .description {
    color: var(--black75, rgba(38, 31, 34, 0.75));
    text-align: center;
    font-family: Bricolage;
    font-size: 21px;
    font-style: normal;
    font-weight: 400;
    line-height: 30px; /* 142.857% */
  }

  .resume-container {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    padding: 40px 0;
  }
  .action-btn {
    color: #FFF;
    font-family: Bricolage;
    font-size: 21px;
    font-style: normal;
    font-weight: 700;
    line-height: 30px;
    border-radius: 100px;
    padding: 36px 48px;
    background: var(--brand-gradient, linear-gradient(90deg, #FE572E 0%, #FC3A79 100%));
    box-shadow: 0px 2.76726px 2.21381px 0px rgba(0, 0, 0, 0.02), 0px 6.6501px 5.32008px 0px rgba(0, 0, 0, 0.03), 0px 12.52155px 10.01724px 0px rgba(0, 0, 0, 0.04), 0px 22.33631px 17.86905px 0px rgba(0, 0, 0, 0.04);
    img {
      width: 20px;
      height: 20px;
      margin-left: 15px;
    }
  }
  @media (max-width: 768px) {

  }
}
</style>