<template>
  <header class="navbar glassy-navbar">
    <div class="navbar-container">
      <div class="brand-section">
        <img src="../assets/icons/brand-icon.png" alt="Brand Icon" class="brand-icon" @click="handleSelect('Home')" />
      </div>
      <nav class="navbar-menu">
        <button class="menu-toggle" @click="toggleMenu">
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
          <span class="icon-bar"></span>
        </button>
        <ul class="menu-items" :class="{ 'is-open': isMenuOpen }">
          <li class="menu-item" :class="{ 'active': activeIndex === 'home' }" @click="handleSelect('Home')">Home</li>
          <li class="menu-item" :class="{ 'active': activeIndex === 'work' }" @click="handleSelect('work')">Work</li>
          <li class="menu-item" :class="{ 'active': activeIndex === 'about' }" @click="handleSelect('About')">About me</li>
          <li class="menu-item" :class="{ 'active': activeIndex === 'contact' }" @click="handleSelect('Contact')">Contact</li>
        </ul>
      </nav>
      <div class="social-section">
        <img src="../assets/icons/dribble-icon.png" alt="Dribble Icon" class="social-icon" />
        <img src="../assets/icons/linkedin-icon.png" alt="LinkedIn Icon" class="social-icon" />
        <img src="../assets/icons/behance-icon.png" alt="Behance Icon" class="social-icon" />
      </div>
    </div>
  </header>
</template>

<script>
import { onMounted, ref, computed } from 'vue';
import { useRouter } from 'vue-router'

export default {
  setup() {
    const router = useRouter();
    const activeIndex = ref('home');
    const isMenuOpen = ref(false);

    onMounted(() => {})

    const handleSelect = (name) => {
      activeIndex.value = name.toLowerCase();
      isMenuOpen.value = false;
      router.push({name});
    };

    const toggleMenu = () => {
      isMenuOpen.value = !isMenuOpen.value;
    };

    const isMobile = computed(() => {
      return window.innerWidth <= 768;
    })

    return {
      activeIndex,
      handleSelect,
      isMobile,
      toggleMenu,
      isMenuOpen
    };
  },
};
</script>

<style scoped>
.glassy-navbar {
  width: 100%;
  box-sizing: border-box;
  height: 74px;
  padding: 0 2.5rem;
  position: sticky;
  top: 0;
  left: 0;
  z-index: 1000;
  background: rgba(255, 224, 230, 0.85);
  backdrop-filter: blur(16px);
  border-bottom: 1.5px solid #fc3a7933;
  box-shadow: 0 4px 24px rgba(252, 58, 121, 0.08), 0 1.5px 6px rgba(0,0,0,0.07);
  display: flex;
  align-items: center;
  justify-content: space-between;
  transition: background 0.3s, box-shadow 0.3s;
}

.navbar-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  min-height: 74px;
  gap: 0;
}

.brand-section {
  display: flex;
  align-items: center;
  height: 74px;
}
.brand-icon {
  width: 38px;
  height: auto;
  cursor: pointer;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(252, 58, 121, 0.10);
  transition: box-shadow 0.2s;
}
.brand-icon:hover {
  box-shadow: 0 4px 16px rgba(252, 58, 121, 0.18);
}

.social-section {
  display: flex;
  align-items: center;
  gap: 18px;
  height: 74px;
}
.social-icon {
  width: 22px;
  height: 22px;
  cursor: pointer;
  opacity: 0.8;
  transition: opacity 0.18s, transform 0.18s;
}
.social-icon:hover {
  opacity: 1;
  transform: scale(1.12);
}

.navbar-menu {
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  height: 74px;
}

.menu-items {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 32px;
  margin: 0;
  padding: 0;
  list-style: none;
  background: none;
  height: 74px;
}

.menu-item {
  list-style: none;
  font-family: Brandon, sans-serif;
  font-weight: 500;
  font-size: 1.08rem;
  letter-spacing: 0.5px;
  text-decoration: none;
  cursor: pointer;
  color: #261F22;
  background: none;
  border: none;
  padding: 8px 18px;
  border-radius: 8px;
  transition: background 0.18s, color 0.18s, box-shadow 0.18s;
  margin: 0;
  position: relative;
  display: flex;
  align-items: center;
  height: 74px;
}
.menu-item:hover, .menu-item.active {
  background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
  color: #fff;
  box-shadow: 0 2px 8px rgba(252, 58, 121, 0.10);
}
.menu-item.active::after {
  content: '';
  display: block;
  width: 18px;
  height: 3px;
  background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
  border-radius: 2px;
  margin: 6px auto 0 auto;
}

button.menu-toggle {
  background: none;
  border: none;
  padding: 0;
  cursor: pointer;
  display: none;
}

.menu-toggle span.icon-bar {
  display: block;
  width: 22px;
  height: 3px;
  margin: 3px 0;
  background-color: #fc3a79;
  border-radius: 2px;
  transition: 0.3s;
}

/* Desktop styles (screens wider than 900px) */
@media only screen and (min-width: 900px) {
  .menu-toggle {
    display: none;
  }
}

/* Mobile styles (screens below 900px) */
@media only screen and (max-width: 899px) {
  .navbar-menu {
    flex-grow: 0;
    height: 74px;
  }
  .menu-toggle {
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    margin-left: 18px;
    z-index: 100;
    background: none;
    border: none;
    height: 74px;
  }
  .menu-items {
    display: none;
    position: absolute;
    top: 74px;
    right: 0;
    left: 0;
    flex-direction: column;
    align-items: center;
    gap: 0;
    background: rgba(255, 224, 230, 0.98);
    box-shadow: 0 4px 24px rgba(252, 58, 121, 0.10);
    border-radius: 0 0 18px 18px;
    padding: 18px 0 12px 0;
    z-index: 999;
    transition: all 0.3s;
  }
  .menu-items.is-open {
    display: flex;
  }
  .menu-item {
    width: 100vw;
    text-align: center;
    font-size: 1.1rem;
    padding: 18px 0;
    border-radius: 0;
    margin: 0;
    background: none;
    color: #261F22;
    height: 54px;
    align-items: center;
    justify-content: center;
    display: flex;
  }
  .menu-item:hover, .menu-item.active {
    background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
    color: #fff;
  }
  .social-section {
    display: none;
  }
}
</style>
