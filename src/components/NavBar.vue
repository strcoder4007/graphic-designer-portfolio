<template>
  <header class="navbar">
    <div class="navbar-container">
      <div class="brand-section">
        <img src="../assets/icons/brand-icon.png" alt="Brand Icon" class="brand-icon" @click="handleSelect('Home')" />
      </div>
      <div class="navbar-menu">
        <button class="menu-toggle" @click="toggleMenu">
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
        </button>
        <ul class="menu-items" :class="{ 'is-open': isMenuOpen }">
          <li class="menu-item" :class="{ 'active': activeIndex === 'home' }" @click="handleSelect('Home')">Home</li>
          <li class="menu-item" :class="{ 'active': activeIndex === 'portfolio' }" @click="handleSelect('Portfolio')">Portfolio</li>
          <li class="menu-item riny-designs" @click="handleSelect('Home')">Riny Designs</li>
          <li class="menu-item" :class="{ 'active': activeIndex === 'about' }" @click="handleSelect('About')">About me</li>
          <li class="menu-item" :class="{ 'active': activeIndex === 'contact' }" @click="handleSelect('Contact')">Contact</li>
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
import { onMounted, ref } from 'vue';
import { useRouter } from 'vue-router'

export default {
  setup() {
    const router = useRouter();
    const activeIndex = ref('home');
    const isMenuOpen = ref(false);

    onMounted(() => {
    })

    const handleSelect = (name) => {
      activeIndex.value = name.toLowerCase();
      isMenuOpen.value = false; // Close menu after selection
      // Handle navigation or route changes based on selected item
      router.push({name});
    };

    const toggleMenu = () => {
      isMenuOpen.value = !isMenuOpen.value;
    };

    return {
      activeIndex,
      handleSelect,
      toggleMenu,
      isMenuOpen
    };
  },
};
</script>

<style lang="scss" scoped>
.navbar {
  height: 100px;
  padding: 0 2rem;
  background-color: #FBE9E9;
  display: flex;
  align-items: center;
  justify-content: space-between;


  .riny-designs {
    color: #261F22;
    font-family: Brandon, sans-serif;
    font-size: 40px;
    font-style: normal;
    font-weight: 900 !important;
    line-height: 42px;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-top: 0px !important;
  }

  .menu-toggle {
    display: none;
  }

  @media (max-width: 768px) {
    .navbar-menu {
      display: none;
      padding: 0;

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
    width: 100%;

    .brand-section,
    .social-section {
      width: auto;
    }

    .brand-icon {
      width: 30px;
      height: auto;
      cursor: pointer;
    }
    .social-icon {
      width: 15px;
      height: auto;
      cursor: pointer;
      margin-left: 15px;

      &:first-child {
        width: 20px;
        margin-bottom: -3px;
      }

      &:last-child {
        width: 20px;
      }
    }

    .navbar-menu {
      display: flex;
      flex-grow: 1;
      padding: 0 150px;

      .menu-items {
        display: flex;
        flex-grow: 1;
        justify-content: space-between;

        .menu-item {
          list-style: none;
          font-weight: bold;
          text-decoration: none;
          cursor: pointer;
          margin-top: 10px;

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
}
</style>