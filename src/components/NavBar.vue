<template>
  <el-header height="80px">
    <el-container class="navbar-container">
      <el-aside width="64px">
        <el-image :src="brandIcon" class="brand-icon" fit="contain"></el-image>
      </el-aside>
      <el-main class="navbar-main">
        <el-menu
          :default-active="activeIndex"
          class="navbar-menu"
          mode="horizontal"
          @select="handleSelect"
        >
          <el-menu-item index="home">Home</el-menu-item>
          <el-menu-item index="portfolio">Portfolio</el-menu-item>
          <div class="center-item">
            <el-menu-item index="riny-designs" style="font-weight: bold">Riny Designs</el-menu-item>
          </div>
          <el-menu-item index="about">About me</el-menu-item>
          <el-menu-item index="contact">Contact</el-menu-item>
        </el-menu>
      </el-main>
      <el-aside width="64px">
        <el-space>
          <el-image src="path/to/dribble-icon.png" class="social-icon"></el-image>
          <el-image src="path/to/linkedin-icon.png" class="social-icon"></el-image>
          <el-image src="path/to/behance-icon.png" class="social-icon"></el-image>
        </el-space>
      </el-aside>
    </el-container>
  </el-header>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const activeIndex = ref('home');

    const handleSelect = (key) => {
      // Handle navigation or route changes based on selected item
      console.log(key);
    };

    return {
      activeIndex,
      handleSelect,
      brandIcon: 'path/to/your/brand/icon.png', // Replace with your brand icon path
    };
  },
};
</script>

<style scoped>
.navbar-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
}

.brand-icon,
.social-icon {
  width: 100%;
  height: 100%;
  cursor: pointer;
}

.navbar-menu {
  display: flex;
  justify-content: space-between;
}

.center-item {
  text-align: center;
}

.navbar-menu a {
  margin: 0 10px;
}

.social-icon {
  margin: 4px; /* Adjust spacing as needed */
}

@media (max-width: 768px) {
  .navbar-menu {
    flex-direction: column;
  }

  .center-item {
    text-align: left !important;
  }
}
</style>
