<template>
  <header class="navbar">
    <div class="navbar-inner">
      <div class="navbar-brand" @click="navigate('Home')">
        <img src="../assets/icons/brand-icon.png" alt="Brand" class="brand-icon" />
      </div>
      <nav :class="['navbar-links', { open: menuOpen }]">
        <a
          v-for="item in navItems"
          :key="item.name"
          :class="{ active: active === item.name }"
          @click="navigate(item.name)"
          href="javascript:void(0);"
        >
          {{ item.label }}
        </a>
        <div class="navbar-social">
          <a href="https://dribbble.com/" target="_blank" rel="noopener">
            <img src="../assets/icons/dribble-icon.png" alt="Dribbble" />
          </a>
          <a href="https://linkedin.com/" target="_blank" rel="noopener">
            <img src="../assets/icons/linkedin-icon.png" alt="LinkedIn" />
          </a>
          <a href="https://behance.net/" target="_blank" rel="noopener">
            <img src="../assets/icons/behance-icon.png" alt="Behance" />
          </a>
        </div>
      </nav>
      <button class="navbar-toggle" @click="menuOpen = !menuOpen" aria-label="Toggle menu">
        <svg width="28" height="28" viewBox="0 0 28 28" fill="none">
          <rect y="6" width="28" height="2.5" rx="1.25" :fill="menuOpen ? '#FC3A79' : '#261F22'" />
          <rect y="13" width="28" height="2.5" rx="1.25" :fill="menuOpen ? '#FC3A79' : '#261F22'" />
          <rect y="20" width="28" height="2.5" rx="1.25" :fill="menuOpen ? '#FC3A79' : '#261F22'" />
        </svg>
      </button>
    </div>
    <div v-if="menuOpen" class="navbar-backdrop" @click="menuOpen = false"></div>
  </header>
</template>

<script setup>
import { ref } from 'vue'
import { useRouter } from 'vue-router'

const router = useRouter()
const menuOpen = ref(false)
const active = ref('Home')

const navItems = [
  { name: 'Home', label: 'Home' },
  { name: 'work', label: 'Work' },
  { name: 'About', label: 'About me' },
  { name: 'Contact', label: 'Contact' }
]

function navigate(name) {
  active.value = name
  menuOpen.value = false
  router.push({ name })
}
</script>

<style scoped>
.navbar {
  --default-bg-color: rgba(252, 207, 196, 0.4);
  width: 100%;
  background: #fff;
  border-bottom: 1.5px solid #fc3a7933;
  box-shadow: 0 2px 12px rgba(252, 58, 121, 0.06);
  position: sticky;
  top: 0;
  left: 0;
  z-index: 1000;
  transition: box-shadow 0.2s, background 0.2s;
}

.navbar-inner {
  max-width: 1200px;
  margin: 0 auto;
  height: 68px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 2rem;
  position: relative;
}

.navbar-brand {
  display: flex;
  align-items: center;
  cursor: pointer;
  gap: 0.7rem;
  user-select: none;
}
.brand-icon {
  width: 36px;
  height: 36px;
  border-radius: 10px;
  box-shadow: 0 2px 8px rgba(252, 58, 121, 0.10);
  transition: box-shadow 0.18s;
}
.brand-icon:hover {
  box-shadow: 0 4px 16px rgba(252, 58, 121, 0.18);
}
.brand-name {
  font-family: 'BricolageGrotesque', 'Brandon', sans-serif;
  font-size: 1.25rem;
  font-weight: 700;
  color: #FC3A79;
  letter-spacing: 0.5px;
}

.navbar-links {
  display: flex;
  align-items: center;
  gap: 2.2rem;
  transition: right 0.3s;
}
.navbar-links a {
  font-family: 'Brandon', sans-serif;
  font-size: 1.05rem;
  font-weight: 500;
  color: #261F22;
  text-decoration: none;
  padding: 7px 16px;
  border-radius: 7px;
  transition: background 0.18s, color 0.18s;
  position: relative;
}
.navbar-links a.active,
.navbar-links a:hover {
  background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
  color: #fff;
}
.navbar-links a.active::after {
  content: '';
  position: absolute;
  left: 50%;
  bottom: 6px;
  transform: translateX(-50%);
  width: 16px;
  height: 3px;
  background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
  border-radius: 2px;
  pointer-events: none;
  opacity: 0.85;
}

.navbar-social {
  display: flex;
  align-items: center;
  gap: 18px;
  margin-left: 1.5rem;
  background: var(--default-bg-color);
  border-radius: 999px;
  padding: 6px 18px;
  box-shadow: 0 2px 8px rgba(252, 58, 121, 0.08);
  transition: box-shadow 0.18s, background 0.18s;
}
.navbar-social:hover {
  background: var(--default-bg-color);
  box-shadow: 0 4px 16px rgba(252, 58, 121, 0.13);
}
.navbar-social a {
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  transition: background 0.18s;
  width: 36px;
  height: 36px;
}
.navbar-social a:hover {
  background: rgb(255, 255, 255);
}
.navbar-social img {
  width: 20px;
  height: 18px;
  opacity: 0.88;
  transition: opacity 0.18s, transform 0.18s;
}
.navbar-social a[href*="dribbble"] img {
  width: 22px;
  height: 20px;
}
.navbar-social a[href*="behance"] img {
  width: 18px;
  height: 16px;
}
.navbar-social img:hover {
  opacity: 1;
  transform: scale(1.15);
}

.navbar-toggle {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  margin-left: 1.2rem;
  padding: 6px;
  z-index: 1201;
}

.navbar-backdrop {
  position: fixed;
  inset: 0;
  background: rgba(38, 31, 34, 0.18);
  z-index: 1200;
  animation: fadeIn 0.2s;
}
@keyframes fadeIn {
  from { opacity: 0; }
  to { opacity: 1; }
}

/* Responsive styles */
@media (max-width: 900px) {
  .navbar-inner {
    padding: 0 1rem;
    height: 62px;
  }
  .navbar-links {
    position: fixed;
    top: 0;
    right: -100vw;
    flex-direction: column;
    align-items: flex-start;
    background: #fff;
    width: 78vw;
    max-width: 340px;
    height: 100vh;
    box-shadow: -2px 0 18px rgba(252, 58, 121, 0.10);
    padding: 90px 2rem 2rem 2rem;
    gap: 1.5rem;
    z-index: 1300;
    transition: right 0.32s cubic-bezier(.7,.2,.2,1);
  }
  .navbar-links.open {
    right: 0;
  }
  .navbar-social {
    margin-left: 0;
    margin-top: 2.5rem;
    gap: 18px;
  }
  .navbar-toggle {
    display: block;
  }
}

@media (max-width: 600px) {
  .navbar-inner {
    padding: 0 0.5rem;
  }
  .navbar-links {
    width: 100vw;
    max-width: 100vw;
    padding: 80px 1.2rem 1.2rem 1.2rem;
  }
  .brand-name {
    font-size: 1.08rem;
  }
}
</style>
