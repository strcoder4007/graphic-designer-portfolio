<template>
  <div class="">
    <el-row>
      <el-col :span="12" v-for="project in projectList" :key="project.id">
        <ProjectComponent
          :name="project.name"
          :description="project.description">
        </ProjectComponent>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import ProjectComponent from './ProjectComponent.vue'
export default {
  name: "ProjectLandingPage",
  data() {
    return {
      projectList: [
        {
          "id": "f86c5e5c-5075-4c5e-b57b-22a7a380de34",
          "name": "E-commerce Platform Redesign",
          "description": "Revamping an online marketplace with modern UI/UX, improved performance, and enhanced customer engagement features."
        },
        {
          "id": "a5a5b332-73d6-4b61-aa60-6b4f6f1a10f7",
          "name": "Mobile App Development",
          "description": "Creating a cross-platform mobile app for seamless user experience across iOS and Android devices."
        },
        {
          "id": "16c2b2e7-5a6e-459d-8aa7-890f2ebc5a0f",
          "name": "Data Analytics Dashboard",
          "description": "Building a comprehensive analytics dashboard to visualize key metrics and trends for business intelligence."
        },
        {
          "id": "8fd7a21c-4f31-491b-9a9c-c53a23e3d1a3",
          "name": "Cloud Migration Strategy",
          "description": "Planning and executing a seamless migration of legacy systems to cloud infrastructure for scalability and efficiency."
        },
        {
          "id": "cf3e6e24-c22e-4a61-97f8-6ff5b1e3a3e0",
          "name": "Blockchain Integration Project",
          "description": "Integrating blockchain technology into existing systems to enhance security, transparency, and transaction efficiency."
        }
      ]
    }
  },
  mounted() {
    
  },
  components: {
    ProjectComponent
  },
};
</script>

<style lang="scss" scoped>
@media (max-width: 768px) {

}
</style>