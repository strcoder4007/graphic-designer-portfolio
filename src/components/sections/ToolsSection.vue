<template>
  <section class="tools-section">
    <h2 class="title">Tools I Use</h2>
    <div class="tools-grid">
      <div
        v-for="(tool, i) in tools"
        :key="tool.name"
        class="tool-card"
        :style="{ animationDelay: (i * 0.08) + 's' }"
      >
        <div class="tool-logo-bg">
          <img :src="tool.logo" :alt="tool.name" class="tool-logo" />
        </div>
        <span class="tool-label">{{ tool.name }}</span>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "ToolsSection",
  data() {
    return {
      tools: [
        {
          name: "Figma",
          logo: "../../assets/tools/figma.png",
        },
        {
          name: "Adobe Photoshop",
          logo: "../../assets/tools/photoshop.png",
        },
        {
          name: "Adobe Illustrator",
          logo: "../../assets/tools/illustrator.png",
        },
        {
          name: "Adobe Firefly",
          logo: "../../assets/tools/firefly.png",
        },
        {
          name: "ChatGPT / Dall-E",
          logo: "../../assets/tools/chatgpt.png",
        },
        {
          name: "Midjourney",
          logo: "../../assets/tools/midjourney.png",
        },
        {
          name: "Runway ML",
          logo: "../../assets/tools/chatgpt.png",
        },
        {
          name: "Mystic 2.5",
          logo: "../../assets/tools/chatgpt.png",
        },
        {
          name: "Stable Diffusion",
          logo: "../../assets/tools/chatgpt.png",
        },
        {
          name: "Claude",
          logo: "../../assets/tools/chatgpt.png",
        },
      ],
    };
  },
};
</script>

<style scoped>
.tools-section {
  width: 100%;
  max-width: 1100px;
  margin: 80px auto 60px auto;
  padding: 48px 24px;
  border-radius: 32px;
  background: rgba(255,255,255,0.45);
  box-shadow: 0 8px 32px rgba(252, 58, 121, 0.08), 0 2px 12px rgba(0,0,0,0.08);
  backdrop-filter: blur(12px);
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  overflow: visible;
}

.title {
  font-family: Brandon, sans-serif;
  font-size: 2.5rem;
  font-weight: 700;
  color: #261F22;
  margin-bottom: 36px;
  letter-spacing: 1px;
  text-align: center;
  background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.tools-grid {
  width: 100%;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
  gap: 36px 32px;
  justify-items: center;
  align-items: stretch;
}

.tool-card {
  background: rgba(255,255,255,0.7);
  border-radius: 20px;
  box-shadow: 0 4px 24px rgba(252, 58, 121, 0.10), 0 1.5px 6px rgba(0,0,0,0.07);
  padding: 32px 18px 24px 18px;
  display: flex;
  flex-direction: column;
  align-items: center;
  transition: transform 0.22s cubic-bezier(.4,2,.6,1), box-shadow 0.22s;
  cursor: pointer;
  position: relative;
  animation: fadeUp 0.7s cubic-bezier(.4,2,.6,1) both;
}
.tool-card:hover {
  transform: translateY(-8px) scale(1.06) rotate(-1deg);
  box-shadow: 0 8px 32px rgba(252, 58, 121, 0.18), 0 2px 12px rgba(0,0,0,0.12);
  background: rgba(255,255,255,0.95);
}

.tool-logo-bg {
  background: linear-gradient(135deg, #ffe0e6 0%, #fff6f0 100%);
  border-radius: 50%;
  width: 64px;
  height: 64px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 18px;
  box-shadow: 0 2px 8px rgba(252, 58, 121, 0.10);
  transition: background 0.3s;
}
.tool-card:hover .tool-logo-bg {
  background: linear-gradient(135deg, #fc3a79 0%, #fe572e 100%);
}

.tool-logo {
  width: 38px;
  height: 38px;
  object-fit: contain;
  filter: drop-shadow(0 2px 6px rgba(252, 58, 121, 0.10));
  transition: filter 0.3s;
}
.tool-card:hover .tool-logo {
  filter: drop-shadow(0 4px 12px rgba(252, 58, 121, 0.18));
}

.tool-label {
  font-family: Bricolage, sans-serif;
  font-size: 1.08rem;
  font-weight: 600;
  color: #261F22;
  margin-top: 6px;
  letter-spacing: 0.5px;
  text-align: center;
  transition: color 0.2s;
}
.tool-card:hover .tool-label {
  color: #FC3A79;
}

@keyframes fadeUp {
  from {
    opacity: 0;
    transform: translateY(40px) scale(0.98);
  }
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

@media (max-width: 900px) {
  .tools-section {
    max-width: 98vw;
    margin: 40px 0 40px 0;
    padding: 32px 8px;
  }
  .tools-grid {
    gap: 24px 12px;
  }
}

@media (max-width: 600px) {
  .tools-section {
    padding: 18px 2px;
    border-radius: 18px;
  }
  .title {
    font-size: 1.5rem;
    margin-bottom: 18px;
  }
  .tools-grid {
    grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
    gap: 16px 6px;
  }
  .tool-card {
    padding: 18px 6px 14px 6px;
    border-radius: 12px;
  }
  .tool-logo-bg {
    width: 38px;
    height: 38px;
    margin-bottom: 10px;
  }
  .tool-logo {
    width: 22px;
    height: 22px;
  }
  .tool-label {
    font-size: 0.95rem;
  }
}
</style>
