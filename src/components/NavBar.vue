<template>
  <header class="navbar">
    <div class="navbar-container">
      <div class="brand-section">
        <img :src="brandIcon" alt="Brand Icon" class="brand-icon" @click="toggleMenu" />
      </div>
      <div class="navbar-menu">
        <button class="menu-toggle" @click="toggleMenu">
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
        </button>
        <ul class="menu-items" :class="{ 'is-open': isMenuOpen }">
          <li class="menu-item" :class="{ 'active': activeIndex === 'home' }" @click="handleSelect('home')">Home</li>
          <li class="menu-item" :class="{ 'active': activeIndex === 'portfolio' }" @click="handleSelect('portfolio')">Portfolio</li>
          <li class="menu-item riny-designs" :class="{ 'active': activeIndex === 'riny-designs' }" @click="handleSelect('riny-designs')">Riny Designs</li>
          <li class="menu-item" :class="{ 'active': activeIndex === 'about' }" @click="handleSelect('about')">About me</li>
          <li class="menu-item" :class="{ 'active': activeIndex === 'contact' }" @click="handleSelect('contact')">Contact</li>
        </ul>
      </div>
      <div class="social-section">
        <img src="../assets/icons/dribble-icon.png" alt="Dribble Icon" class="social-icon" />
        <img src="../assets/icons/linkedin-icon.png" alt="LinkedIn Icon" class="social-icon" />
        <img src="../assets/icons/behance-icon.png" alt="Behance Icon" class="social-icon" />
      </div>
    </div>
  </header>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const activeIndex = ref('home');
    const isMenuOpen = ref(false);

    const handleSelect = (key) => {
      // Handle navigation or route changes based on selected item
      activeIndex.value = key;
      isMenuOpen.value = false; // Close menu after selection
    };

    const toggleMenu = () => {
      isMenuOpen.value = !isMenuOpen.value;
    };

    return {
      activeIndex,
      handleSelect,
      toggleMenu,
      isMenuOpen,
      brandIcon: 'path/to/your/brand/icon.png', // Replace with your brand icon path
    };
  },
};
</script>

<style lang="scss" scoped>
.navbar {
  height: 100px;
  padding: 0 1rem;
  background-color: #FBE9E9;
  display: flex;
  align-items: center;
  justify-content: space-between;

  @media (max-width: 768px) {
    .navbar-menu {
      display: none;

      &.is-open {
        display: block;
        position: absolute;
        top: 100%;
        left: 0;
        right: 0;
        background-color: #FBE9E9;
        padding: 1rem;
        box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
        opacity: 1;
        transform: translateY(0);
        transition: all 0.3s ease-in-out;
      }
    }

    .menu-toggle {
      display: block;
    }
  }

  .navbar-container {
    display: flex;
    align-items: center;
    flex-grow: 1;
    justify-content: space-between;
    width: 100%;

    .brand-section,
    .social-section {
      width: auto;
    }

    .brand-icon,
    .social-icon {
      width: 15px;
      height: auto;
      cursor: pointer;
      margin-left: 15px;

      &:last-child {
        width: 20px;
      }
    }

    .navbar-menu {
      width: auto;
      display: flex;
      flex-grow: 1;
      align-items: center;

      .menu-items {
        display: flex;
        flex-grow: 1;
        justify-content: space-between;

        .menu-item {
          list-style: none;
          margin: 0 10px;
          font-weight: bold;
          text-decoration: none;
          cursor: pointer;

          &.active::after {
            content: '';
            display: block;
            width: 5px;
            height: 5px;
            background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
            border-radius: 50%;
            margin: 0 auto;
            margin-top: 5px;
          }
        }
      }
    }
  }

  .riny-designs {
    color: #261F22;
    font-family: Brandon, sans-serif;
    font-size: 38px;
    font-style: normal;
    font-weight: 700;
    line-height: 42px;
    letter-spacing: 5.7px;
    text-transform: uppercase;
  }

  .menu-toggle {
    display: none;
  }
}
</style>