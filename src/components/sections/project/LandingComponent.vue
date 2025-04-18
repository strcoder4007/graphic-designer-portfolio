<template>
  <div class="project-landing-page">
    <el-row>
      <el-col :md="12" :xl="8" v-for="project in projectList" :key="project.id" class="project-container">
        <div class="cvfy-container">
          <div class="cvfy-card">
            <div class="card-header">
              <div class="window-controls">
                <span class="control red"></span>
                <span class="control yellow"></span>
                <span class="control green"></span>
              </div>
              <span class="app-title">{{ project.name }}</span>
            </div>
            <div class="card-body image-container">
              <img v-if="project.image === 'dashboard_design'" src="../../../assets/projects/dashboard_design.png" />
              <img v-if="project.image === 'illustration'" src="../../../assets/projects/illustration.png" />
              <img v-if="project.image === 'website_design'" src="../../../assets/projects/website_design.png" />
              <img v-if="project.image === 'mobile_app_design'" src="../../../assets/projects/mobile_app_design.png" />
              <img v-if="project.image === 'ui_ux_design'" src="../../../assets/projects/ui_ux_design.png" />
            </div>
          </div>
          <div class="project-name">{{  project.name }}</div>
          <div class="project-description">
            {{ project.description }}
          </div>
          <div class="links-container">
            <div class="figma" @click="goToLink('figma')">Figma <img src="../../../assets/icons/arrow-right.png" alt="Arrow Right Icon" /></div>
            <!-- <div class="behance" @click="goToLink('behance')">Behance <img src="../../../assets/icons/arrow-right.png" alt="Arrow Right Icon" /></div>
            <div class="live" @click="goToLink('live')">Live <img src="../../../assets/icons/arrow-right.png" alt="Arrow Right Icon" /></div>
            <div class="code" @click="goToLink('code')">Code <img src="../../../assets/icons/arrow-right.png" alt="Arrow Right Icon" /></div> -->
          </div>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: "ProjectLandingPage",

  setup() {
    const goToLink = (name) => {
      if (name === 'figma')
        window.open('https://www.figma.com/design/hldHS5PGFtbHdixRlBe6YP/New-PORTFOLIO?node-id=120-112&t=S4MDqijKWPgN5Gf0-0', '_blank');
    }
    return {
      goToLink
    }
  },
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
  padding: 0 16px;
  width: 100%;
  box-sizing: border-box;
  overflow-x: hidden;
}

/* Prevent Element Plus grid from causing overflow */
.el-row, .el-col {
  box-sizing: border-box;
  width: 100%;
  margin: 0;
  padding: 0;
}
.image-container {
    width: 100%;
    max-width: 400px;
    height: 250px;
    background-color: #f0f0f0; 
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    overflow: hidden; 
}
.image-container.centered {
    display: flex;
    justify-content: center;
    align-items: center;
}



.cvfy-container {
  width: 100%;
  max-width: 400px;
  margin: 50px auto;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.cvfy-card {
  width: 100%;
  box-sizing: border-box;
  background-color: white;
  border-radius: 8px;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  margin-bottom: 40px;
  cursor: pointer;
  transition: box-shadow 0.3s, transform 0.3s;
  position: relative;
}
.cvfy-card:hover {
  box-shadow: 0 8px 32px rgba(252, 58, 121, 0.18), 0 2px 12px rgba(0,0,0,0.12);
  transform: translateY(-6px) scale(1.03);
}
.image-container {
  width: 100%;
  max-width: 400px;
  height: 250px;
  background-color: #f0f0f0; 
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  overflow: hidden; 
  transition: transform 0.3s;
}
.cvfy-card:hover .image-container img {
  transform: scale(1.08);
}
.image-container img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s;
}

.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px 10px 10px;
  border-bottom: 1px solid #ebeef5;
  height: 5px;
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

.control.red { background-color: #cccccc; }
.control.yellow { background-color: #cccccc; }
.control.green { background-color: #cccccc; }

.app-title {
  font-size: 13px;
  margin: 0;
  font-weight: 500;
}


.project-name {
  font-size: 25px;
  font-weight: 600;
  font-family: 'Brandon';
  display: block;
  text-align: left;
  margin-top: 8px;
  margin-bottom: 4px;
}

.project-description {
  font-size: 15px;
  font-family: 'Bricolage';
  display: block;
  text-align: left;
  margin: 10px 0 16px 0;
}

.links-container {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  gap: 18px;
  margin-bottom: 8px;
}
.live, .code, .behance, .figma {
  font-size: 18px;
  font-weight: 500;
  font-family: 'Brandon';
  margin-right: 0;
  cursor: pointer;
  display: flex;
  align-items: center;
  gap: 4px;
}
.live:hover, .code:hover, .behance:hover, .figma:hover {
  text-decoration: underline;
}

@media (max-width: 768px) {
  .project-landing-page {
    width: 100%;
    margin: 60px 0;
    padding: 0 5px;
    box-sizing: border-box;
  }
}
</style>
