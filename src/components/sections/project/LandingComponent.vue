<template>
  <div class="project-landing-page">
    <el-row>
      <el-col :span="12" v-for="project in projectList" :key="project.id" class="project-container">
        <!-- <div class="image-container">
          <img v-if="project.image === 'dashboard_design'" src="../../../assets/projects/dashboard_design.png" />
          <img v-if="project.image === 'illustration'" src="../../../assets/projects/illustration.png" />
          <img v-if="project.image === 'website_design'" src="../../../assets/projects/website_design.png" />
          <img v-if="project.image === 'mobile_app_design'" src="../../../assets/projects/mobile_app_design.png" />
          <img v-if="project.image === 'ui_ux_design'" src="../../../assets/projects/ui_ux_design.png" />
        </div>
        <div class="project-name">{{ project.name }}</div>
        <div class="project-description">{{ project.description }}</div>
        <div class="links-container">
          <div class="live">Live</div>
          <div class="code">Code</div>
        </div> -->


        <div class="cvfy-container">
          <div class="cvfy-card">
            <div class="card-header">
              <div class="window-controls">
                <span class="control red"></span>
                <span class="control yellow"></span>
                <span class="control green"></span>
              </div>
              <h1 class="app-title">{{ project.name }}</h1>
            </div>
            <div class="card-body">
              <!-- Image -->
            </div>
          </div>
          <div class="description">
            {{ project.description }}
          </div>
        </div>




      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: "ProjectLandingPage",
  data() {
    return {
      projectList: [
        {
          "id": "f86c5e5c-5075-4c5e-b57b-22a7a380de34",
          "name": "Website Designs",
          "image": "website_design",
          "description": "Revamping an online marketplace with modern UI/UX, improved performance, and enhanced customer engagement features."
        },
        {
          "id": "a5a5b332-73d6-4b61-aa60-6b4f6f1a10f7",
          "name": "Mobile App Design",
          "image": "mobile_app_design",
          "description": "Creating a cross-platform mobile app for seamless user experience across iOS and Android devices."
        },
        {
          "id": "16c2b2e7-5a6e-459d-8aa7-890f2ebc5a0f",
          "name": "Dashboard Designs",
          "image": "dashboard_design",
          "description": "Building a comprehensive analytics dashboard to visualize key metrics and trends for business intelligence."
        },
        {
          "id": "8fd7a21c-4f31-491b-9a9c-c53a23e3d1a3",
          "name": "UI/UX Designs",
          "image": "ui_ux_design",
          "description": "Planning and executing a seamless migration of legacy systems to cloud infrastructure for scalability and efficiency."
        },
        {
          "id": "cf3e6e24-c22e-4a61-97f8-6ff5b1e3a3e0",
          "name": "Illustrations",
          "image": "illustration",
          "description": "Integrating blockchain technology into existing systems to enhance security, transparency, and transaction efficiency."
        }
      ]
    }
  },
  mounted() {
    
  },
  components: {
  },
};
</script>

<style lang="scss" scoped>
.project-landing-page {
  margin: 80px auto;
  .project-container {

  }
}
// .image-container {
//   width: 100%;
//   max-width: 400px;
//   height: 0;
//   padding-bottom: 56.25%; 
//   position: relative;
//   overflow: hidden;
//   background-color: lightblue;
//   img {
//     position: absolute;
//     top: 0;
//     left: 0;
//     width: 100%;
//     height: auto;
//     object-fit: cover;
//   }
// } 



.cvfy-container {
  max-width: 400px;
  margin: 50px auto;
}

.cvfy-card {
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  margin-bottom: 40px;
}

.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px 10px 10px;
  border-bottom: 1px solid #ebeef5;
  height: 10px;
}

.card-body {
  height: 200px;
}

.window-controls {
  display: flex;
  gap: 5px;
}

.control {
  width: 9px;
  height: 9px;
  border-radius: 50%;
}

.control.red { background-color: #ff5f56; }
.control.yellow { background-color: #ffbd2e; }
.control.green { background-color: #27c93f; }

.app-title {
  font-size: 15px;
  margin: 0;
}

@media (max-width: 768px) {

}
</style>