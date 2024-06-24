<template>
  <div class="portfolio-page">
    <div class="greetings">Projects</div>
    <LandingComponent></LandingComponent>
    <FooterSection></FooterSection>
  </div>
</template>

<script>
import FooterSection from "./sections/FooterSection.vue";
import LandingComponent from "./sections/project/LandingComponent.vue"
export default {
  name: "PortfolioPage",
  mounted() {
  },
  components: {
    FooterSection,
    LandingComponent
  },
};
</script>

<style scoped>
.portfolio-page {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  height: auto;
  overflow: scroll;
  background-color: transparent;
}
.greetings {
  margin-top: 100px;
  color: var(--Black, #261F22);
  font-family: Brandon;
  font-size: 59px;
  font-style: normal;
  font-weight: 700;
  line-height: 72px; /* 122.034% */
  letter-spacing: -1.77px;
}
</style>
  