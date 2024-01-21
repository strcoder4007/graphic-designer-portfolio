<template>
  <div>
    <NavBar></NavBar>
    <IntroSection></IntroSection>
    <WorkSection></WorkSection>
    <FreelanceSection></FreelanceSection>
    <FooterSection></FooterSection>
  </div>
</template>

<script>
import NavBar from "./NavBar.vue";
import IntroSection from "./IntroSection.vue";
import WorkSection from "./WorkSection.vue";
import FreelanceSection from "./FreelanceSection.vue";
import FooterSection from "./FooterSection.vue";
export default {
  name: "LandingPage",
  props: {
    msg: String,
  },
  components: {
    NavBar,
    IntroSection,
    WorkSection,
    FreelanceSection,
    FooterSection
  },
};
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
