<template>
  <div>
    <IntroSection></IntroSection>
    <WorkSection></WorkSection>
    <FreelanceSection></FreelanceSection>
    <FooterSection></FooterSection>
  </div>
</template>

<script>
import IntroSection from "./sections/IntroSection.vue";
import WorkSection from "./sections/WorkSection.vue";
import FreelanceSection from "./sections/FreelanceSection.vue";
import FooterSection from "./sections/FooterSection.vue";
export default {
  name: "LandingPage",
  props: {
    msg: String,
  },
  components: {
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
