<template>
  <div class="portfolio-page">
      My work
  </div>
</template>

<script>
export default {
  name: "PortfolioPage",
  mounted() {
    console.log('PortfolioPage mounted')
  },
  components: {
  },
};
</script>

<style scoped>
.portfolio-page {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background-color: #f5f5f5;
}
</style>
  