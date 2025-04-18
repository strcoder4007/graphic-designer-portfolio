<template>
  <NavBar></NavBar>
  <router-view></router-view>
</template>

<script>
import NavBar from "./components/NavBar.vue";

export default {
  name: "App",
  components: {
    NavBar
  }
};
</script>

<style>
@font-face {
  font-family: 'Bricolage';
  src: url('./assets/fonts/BricolageGrotesque.ttf');
}
@font-face {
  font-family: 'Brandon';
  src: url('./assets/fonts/Brandon_reg.otf');
}
@font-face {
  font-family: 'Neue Montreal';
  src: url('./assets/fonts/NeueMontreal-Regular.otf');
  font-weight: 400;
  font-style: normal;
}
@font-face {
  font-family: 'Neue Montreal';
  src: url('./assets/fonts/NeueMontreal-Medium.otf');
  font-weight: 500;
  font-style: normal;
}
@font-face {
  font-family: 'Neue Montreal';
  src: url('./assets/fonts/NeueMontreal-Bold.otf');
  font-weight: 700;
  font-style: normal;
}
@font-face {
  font-family: 'Neue Montreal';
  src: url('./assets/fonts/NeueMontreal-Light.otf');
  font-weight: 300;
  font-style: normal;
}

html {
  scroll-behavior: smooth;
  height: auto;
  width: 100%;
  overflow-x: hidden;
  box-sizing: border-box;
}

/* Apply box-sizing globally for all elements */
*, *::before, *::after {
  box-sizing: inherit;
}

#app {
  font-family: 'Neue Montreal', Bricolage, Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  opacity: 0; /* Start invisible */
  animation: fade-in 1s ease-in-out forwards;
  width: 100%;
  min-height: 100vh;
  box-sizing: border-box;
}
@keyframes fade-in {
  from { opacity: 0; }
  to { opacity: 1; }
}
body {
  margin: 0;
  width: 100%;
  min-height: 100vh;
  overflow-x: hidden;
  box-sizing: border-box;
  /* Extra subtle linear gradient between #FE572E and #FC3A79 */
  background: linear-gradient(120deg, rgba(252, 207, 196, 0.4) 0%, rgba(239, 118, 156, 0.3) 100%);
  position: relative;
}
body::before, body::after, body::blob1, body::blob2, body::blob3 {
  content: "";
  position: fixed;
  z-index: -1;
  border-radius: 50%;
  filter: blur(70px);
  opacity: 0.35;
  pointer-events: none;
  animation: blob-move-1 18s ease-in-out infinite alternate;
  transition: background 0.5s, opacity 0.5s;
}
body::before {
  width: 520px;
  height: 520px;
  left: -200px;
  top: -140px;
  background: radial-gradient(circle at 30% 30%, #ffe0e6 0%, #fc3a79 100%);
  animation-name: blob-move-1;
  animation-delay: 0s;
}
body::after {
  width: 440px;
  height: 440px;
  right: -180px;
  bottom: -120px;
  background: radial-gradient(circle at 70% 70%, #fc3a79 0%, #b82a5a 100%);
  animation-name: blob-move-2;
  animation-delay: 6s;
}
body::blob1 {
  width: 340px;
  height: 340px;
  left: 60vw;
  top: 60vh;
  background: radial-gradient(circle at 60% 60%, #ffe0e6 0%, #fc3a79 100%);
  animation-name: blob-move-3;
  animation-delay: 3s;
}
body::blob2 {
  width: 300px;
  height: 300px;
  left: 40vw;
  top: 10vh;
  background: radial-gradient(circle at 40% 40%, #fc3a79 0%, #ffe0e6 100%);
  animation-name: blob-move-4;
  animation-delay: 9s;
}
body::blob3 {
  width: 260px;
  height: 260px;
  right: 10vw;
  top: 40vh;
  background: radial-gradient(circle at 60% 60%, #b82a5a 0%, #ffe0e6 100%);
  animation-name: blob-move-5;
  animation-delay: 12s;
}
@keyframes blob-move-1 {
  0% { transform: scale(1) translateY(0) translateX(0);}
  50% { transform: scale(1.18) translateY(60px) translateX(40px);}
  100% { transform: scale(1) translateY(-30px) translateX(-30px);}
}
@keyframes blob-move-2 {
  0% { transform: scale(1) translateY(0) translateX(0);}
  50% { transform: scale(1.12) translateY(-40px) translateX(-60px);}
  100% { transform: scale(1) translateY(30px) translateX(30px);}
}
@keyframes blob-move-3 {
  0% { transform: scale(1) translateY(0) translateX(0);}
  50% { transform: scale(1.08) translateY(30px) translateX(-30px);}
  100% { transform: scale(1) translateY(-20px) translateX(20px);}
}
@keyframes blob-move-4 {
  0% { transform: scale(1) translateY(0) translateX(0);}
  50% { transform: scale(1.15) translateY(-20px) translateX(20px);}
  100% { transform: scale(1) translateY(20px) translateX(-20px);}
}
@keyframes blob-move-5 {
  0% { transform: scale(1) translateY(0) translateX(0);}
  50% { transform: scale(1.1) translateY(20px) translateX(-20px);}
  100% { transform: scale(1) translateY(-20px) translateX(20px);}
}
button:hover {
  cursor: pointer;
  transform: scale(1.05); /* Slightly enlarge on hover */
  transition: transform 0.2s ease-in-out;
}

button:active {
  transform: translateY(2px); /* Slightly sink on press */
  transition: transform 0.1s ease-in-out;
}

input:focus {
  border-color: #f00; /* Change border color on focus */
  transition: border-color 0.2s ease-in-out;
}

.el-message__content {
  font-family: Bricolage;
}

/* Custom design for el-button */
.el-button {
  background: linear-gradient(90deg, rgba(254,87,46,0.13) 0%, rgba(252,58,121,0.13) 100%);
  color: #FC3A79;
  border: none;
  border-radius: 14px;
  font-family: 'Neue Montreal', Bricolage, 'Brandon', Arial, sans-serif;
  font-size: 1.08rem;
  font-weight: 500;
  padding: 12px 32px;
  box-shadow: 0 2px 8px rgba(252, 58, 121, 0.07);
  transition: background 0.22s, color 0.22s, box-shadow 0.22s, transform 0.18s;
  outline: none;
  cursor: pointer;
}
.el-button:hover,
.el-button:focus {
  background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
  color: #fff;
  box-shadow: 0 4px 16px rgba(252, 58, 121, 0.13);
  transform: translateY(-2px) scale(1.04);
}
</style>
