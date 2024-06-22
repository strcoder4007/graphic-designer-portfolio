<template>
  <div>
    <div class="image-container"></div>
    <div class="project-name">{{ name }}</div>
    <div class="project-description">{{ description }}</div>
    <div class="links-container">
      <div class="live">Live</div>
      <div class="code">Code</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProjectComponent",
  props: {
    name: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    }
  },
  components: {
  },
};
</script>

<style lang="scss" scoped>
@media (max-width: 768px) {

}
</style>