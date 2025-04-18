<template>
  <div>
    <div class="about-page">
      <el-row>
        <el-col :span="24">
          <span class="header">About Riny Yadav</span>
          <span class="description" v-html="description"></span>
          <el-row class="image-section">
            <el-col :md="12"><img src="../assets/portrait/one.png"></el-col>
            <el-col :md="12"><img src="../assets/portrait/two.png"></el-col>
          </el-row>
        </el-col>
      </el-row>
      <div class="promises-header">What I Deliver</div>
      <el-row>
        <el-col :md="12" class="promises">
          <img src="../assets/icons/clock.svg">
          <span class="promise-subheader">AI-Driven Speed & Reliability</span>
          <span class="promise-description">Harnessing the power of AI, I deliver projects with unmatched speed and precision—always on time, every time.</span>
        </el-col>
        <el-col :md="12" class="promises">
          <img src="../assets/icons/quality.svg">
          <span class="promise-subheader">Data-Optimized Quality</span>
          <span class="promise-description">My designs are continuously refined using AI insights, ensuring pixel-perfect quality and optimal user engagement for every project.</span>
        </el-col>
        <el-col :md="12" class="promises">
          <img src="../assets/icons/rocket.svg">
          <span class="promise-subheader">Adaptive & Scalable Web Design</span>
          <span class="promise-description">I create intelligent, responsive interfaces that adapt to user needs and business goals, scaling effortlessly across platforms and audiences.</span>
        </el-col>
        <el-col :md="12" class="promises">
          <img src="../assets/icons/phone.svg">
          <span class="promise-subheader">Intelligent Mobile Solutions</span>
          <span class="promise-description">From ideation to launch, I design mobile apps powered by AI—delivering seamless, intuitive experiences that drive results on iOS and Android.</span>
        </el-col>
      </el-row>
    </div>
    <ToolsSection></ToolsSection>
    <FreelanceSection class="freelance-section"></FreelanceSection>
    <FooterSection></FooterSection>
  </div>

</template>

<script>
import FooterSection from './sections/FooterSection.vue';
import ToolsSection from './sections/ToolsSection.vue';
import FreelanceSection from './sections/FreelanceSection.vue';

export default {
  name: "AboutPage",
  mounted() {
    
  },
  setup() {
    const description = `I am Riny, your AI-powered graphic designer, blending advanced artificial intelligence with creative expertise to deliver next-generation digital experiences. My approach leverages data-driven insights, rapid prototyping, and adaptive design to help brands and businesses stay ahead in a fast-evolving digital world.<br><br>
    From intuitive user interfaces to visually striking graphics, I specialize in transforming ideas into scalable, high-impact solutions—faster and smarter. Collaborate with me to unlock the full potential of AI-driven design for your business.`;
    return {
      description
    }
  },
  components: {
    FreelanceSection,
    FooterSection,
    ToolsSection
},
};
</script>

<style lang="scss" scoped>
.about-page {
  height: auto;
  min-height: calc(100vh - 100px);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: baseline;
  margin: 200px 150px 50px 150px;
  text-align: left;
}

.freelance-section {
  margin-top: 80px;
}

.header {
  display: block;
  background-image: linear-gradient(to right, #FE572E 0%, #FC3A79 100%);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;

  font-family: "Brandon";
  font-size: 84px;
  font-style: normal;
  font-weight: 700;
  line-height: 112px;
  margin-bottom: 40px;
}
.description {
  display: block;
  color: var(--black75, rgba(38, 31, 34, 0.75));
  font-family: Brandon;
  font-size: 21px;
  font-style: normal;
  font-weight: 400;
  line-height: 30px;
  width: auto;
  min-width: 400px;
  margin-bottom: 40px;
}

.image-section {
    img {
      width: 100%;
      height: auto;
      object-fit: contain;
      margin-bottom: 40px;
    }
} 

.promises-header {
  color: var(--Black, #261F22);
  font-family: "Brandon";
  font-size: 59px;
  font-style: normal;
  font-weight: 330;
  line-height: 72px; 
  letter-spacing: -1.77px;
  margin: 10px 0 100px 0;
}

.promises {
  padding: 0 40px 40px 0;
  margin-bottom: 50px;
  img {
    width: 64px;
    height: 64px;
  }
  .promise-subheader {
    display: block;
    color: var(--Black, #261F22);
    font-family: "Brandon";
    font-size: 30px;
    font-style: normal;
    font-weight: 450;
    line-height: 40px;
    margin-bottom: 30px;
    margin-top: 10px;
  }
  .promise-description {
    color: var(--black75, rgba(38, 31, 34, 0.75));
    font-family: Bricolage;
    font-size: 17px;
    font-style: normal;
    font-weight: 400;
    line-height: 30px;
  }
}
@media (max-width: 768px) {
  .about-page {
    height: auto;
    min-height: calc(100vh - 100px);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: baseline;
    margin: 100px 30px 5px 50px;
    text-align: left;
  }

  .freelance-section {
    margin-top: 40px;
  }

  .header {
    display: block;
    background-image: linear-gradient(to right, #FE572E 0%, #FC3A79 100%);
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    -moz-text-fill-color: transparent;

    font-family: "Brandon";
    font-size: 32px;
    font-style: normal;
    font-weight: 700;
    line-height: 40px;
    margin-bottom: 20px;
  }
  .description {
    display: block;
    color: var(--black75, rgba(38, 31, 34, 0.75));
    font-family: Brandon;
    font-size: 18px;
    font-style: normal;
    font-weight: 400;
    line-height: 20px;
    width: auto;
    min-width: 100%;
    margin-bottom: 20px;
  }

  .image-section {
      img {
        width: 100%;
        height: auto;
        object-fit: contain;
        margin-bottom: 10px;
      }
  } 

  .promises-header {
    color: var(--Black, #261F22);
    font-family: "Brandon";
    font-size: 30px;
    font-style: normal;
    font-weight: 330;
    line-height: 40px; 
    margin: 30px 0 40px 0;
  }

  .promises {
    padding: 0 10px 10px 0;
    margin-bottom: 40px;
    img {
      width: 40px;
      height: 40px;
    }
    .promise-subheader {
      display: block;
      font-size: 18px;
      font-style: normal;
      font-weight: 600;
      line-height: 25px;
      margin-bottom: 20px;
      margin-top: 10px;
    }
    .promise-description {
      font-size: 13px;
      font-style: normal;
      font-weight: 400;
      line-height: 15px;
    }
  }
}

</style>
