<template>
  <section class="project-landing">
    <h1 class="project-landing-title">My Projects</h1>
    <div class="project-category" v-for="category in categories" :key="category.name">
      <div class="category-header">
        <span class="category-icon" v-if="category.iconType === 'svg'">
          <span v-html="category.icon"></span>
        </span>
        <span class="category-icon" v-else-if="category.iconType === 'img'">
          <img :src="category.icon" :alt="category.name + ' icon'" loading="lazy" />
        </span>
        <span class="category-title">{{ category.name }}</span>
      </div>
      <div class="project-list">
        <div class="project-card" v-for="project in category.projects" :key="project.id">
          <div class="project-image">
            <img :src="project.image" :alt="project.name" loading="lazy" />
          </div>
          <div class="project-info">
            <div class="project-name">{{ project.name }}</div>
            <div class="project-description">{{ project.description }}</div>
            <div class="project-links" v-if="project.links">
              <a
                v-for="link in project.links"
                :key="link.label"
                :href="link.url"
                class="project-link"
                target="_blank"
                rel="noopener"
              >
                {{ link.label }}
                <img src="../../../assets/icons/arrow-right.png" alt="Arrow Right" loading="lazy" />
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import websiteDesignImg from "../../../assets/projects/website_design.png";
import websiteRedesignImg from "../../../assets/projects/website_redesign.png";
import mobileAppDesignImg from "../../../assets/projects/mobile_app_design.png";
import dashboardDesignImg from "../../../assets/projects/dashboard_design.png";
import uiuxDesignImg from "../../../assets/projects/ui_ux_design.png";
import illustrationImg from "../../../assets/projects/illustration.png";
import infographicImg from "../../../assets/projects/infographic.png";
import posterBannerImg from "../../../assets/projects/poster_banner.png";


const illustrationSVG = `
<svg width="38" height="38" viewBox="0 0 38 38" fill="none">
  <ellipse cx="19" cy="19" rx="15" ry="10" fill="#FC3A79"/>
  <ellipse cx="19" cy="19" rx="8" ry="5" fill="#fff"/>
  <ellipse cx="19" cy="19" rx="3" ry="2" fill="#FE572E"/>
</svg>
`;

const aiSVG = `
<svg width="38" height="38" viewBox="0 0 38 38" fill="none">
  <rect x="4" y="4" width="30" height="30" rx="15" fill="#FE572E"/>
  <path d="M19 10v18M10 19h18" stroke="#fff" stroke-width="2" stroke-linecap="round"/>
  <circle cx="19" cy="19" r="4" fill="#FC3A79"/>
</svg>
`;


const phoneIcon = `
<svg width="38" height="38" viewBox="0 0 38 38" fill="none">
  <rect x="8" y="6" width="22" height="26" rx="6" fill="#FE572E"/>
  <rect x="13" y="10" width="12" height="16" rx="3" fill="#fff"/>
  <circle cx="19" cy="28" r="2" fill="#FC3A79"/>
</svg>
`;

export default {
  name: "LandingComponent",
  data() {
    return {
      categories: [
        {
          name: "Website Design & UI/UX",
          iconType: "img",
          icon: websiteDesignImg,
          projects: [
            {
              id: "web1",
              name: "Modern Portfolio",
              image: websiteDesignImg,
              description: "A sleek, responsive portfolio website for a creative professional.",
              links: [
                { label: "Live", url: "#" },
                { label: "Figma", url: "https://www.figma.com/" }
              ]
            },
            {
              id: "web2",
              name: "E-commerce Redesign",
              image: websiteRedesignImg,
              description: "Revamping an online store with a focus on UX and conversion.",
              links: [
                { label: "Live", url: "#" }
              ]
            },
            {
              id: "uiux1",
              name: "SaaS Platform UI",
              image: uiuxDesignImg,
              description: "Designing intuitive interfaces for a SaaS productivity tool.",
              links: [
                { label: "Figma", url: "https://www.figma.com/" }
              ]
            },
            {
              id: "dash1",
              name: "Analytics Dashboard",
              image: dashboardDesignImg,
              description: "A comprehensive dashboard for visualizing business metrics.",
              links: [
                { label: "Figma", url: "https://www.figma.com/" }
              ]
            },
            {
              id: "web3",
              name: "Landing Page Concept",
              image: websiteDesignImg,
              description: "A vibrant landing page for a new SaaS product launch.",
              links: []
            },
          ]
        },
        {
          name: "AI-Generation Projects",
          iconType: "svg",
          icon: aiSVG,
          projects: [
            {
              id: "ai1",
              name: "RunwayML Video Generation",
              image: illustrationImg,
              description: "Short films and creative promos generated using RunwayML's Gen-2 AI video tools.",
              links: [
                { label: "RunwayML", url: "https://runwayml.com/" }
              ]
            },
            {
              id: "ai2",
              name: "Stable Diffusion Artworks",
              image: illustrationImg,
              description: "A series of digital artworks created with Stable Diffusion for concept and editorial use.",
              links: [
                { label: "Stable Diffusion", url: "https://stability.ai/" }
              ]
            },
            {
              id: "ai3",
              name: "Midjourney Visuals",
              image: illustrationImg,
              description: "Experimental visuals and illustrations generated with Midjourney AI.",
              links: [
                { label: "Midjourney", url: "https://www.midjourney.com/" }
              ]
            }
          ]
        },
        {
          name: "Mobile App Design",
          iconType: "svg",
          icon: phoneIcon,
          projects: [
            {
              id: "mob1",
              name: "Fitness Tracker App",
              image: mobileAppDesignImg,
              description: "A cross-platform app for tracking workouts and health metrics.",
              links: [
                { label: "Figma", url: "https://www.figma.com/" }
              ]
            },
            {
              id: "mob3",
              name: "Finance Manager",
              image: mobileAppDesignImg,
              description: "A modern app for managing personal finances and budgets.",
              links: []
            }
          ]
        },
        {
          name: "Illustrations",
          iconType: "svg",
          icon: illustrationSVG,
          projects: [
            {
              id: "ill1",
              name: "Editorial Illustration",
              image: illustrationImg,
              description: "Custom illustrations for a tech magazine feature.",
              links: []
            },
            {
              id: "ill2",
              name: "Infographic Series",
              image: infographicImg,
              description: "A set of infographics for a data-driven marketing campaign.",
              links: []
            },
            {
              id: "ill3",
              name: "Poster & Banner",
              image: posterBannerImg,
              description: "Event posters and banners for a creative conference.",
              links: []
            }
          ]
        },
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
/* ... (unchanged styles from previous version) ... */
.project-landing {
  width: 100%;
  max-width: 1200px;
  margin: 80px auto 40px auto;
  padding: 0 16px;
  box-sizing: border-box;
}
.project-landing-title {
  font-family: 'Neue Montreal', 'Brandon', Arial, sans-serif;
  font-size: 2.8rem;
  font-weight: 700;
  text-align: center;
  margin-bottom: 48px;
  background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
.project-category {
  margin-bottom: 56px;
}
.category-header {
  display: flex;
  align-items: center;
  gap: 18px;
  margin-bottom: 18px;
}
.category-icon img, .category-icon span svg {
  width: 38px;
  height: 38px;
  border-radius: 10px;
  box-shadow: 0 2px 8px rgba(252, 58, 121, 0.10);
  background: #fff;
  display: block;
}
.category-title {
  font-family: 'Neue Montreal', 'Brandon', Arial, sans-serif;
  font-size: 1.6rem;
  font-weight: 700;
  color: #FC3A79;
  letter-spacing: 0.5px;
  background: none;
}
.project-list {
  display: flex;
  flex-wrap: wrap;
  gap: 32px;
  justify-content: flex-start;
}
.project-card {
  background: #fff;
  border-radius: 18px;
  box-shadow: 0 4px 24px rgba(252, 58, 121, 0.10), 0 1.5px 6px rgba(0,0,0,0.07);
  width: 320px;
  min-width: 260px;
  max-width: 100%;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  transition: box-shadow 0.22s, transform 0.22s;
  cursor: pointer;
  overflow: hidden;
  position: relative;
}
.project-card:hover {
  box-shadow: 0 8px 32px rgba(252, 58, 121, 0.18), 0 2px 12px rgba(0,0,0,0.12);
  transform: translateY(-6px) scale(1.03);
}
.project-image {
  width: 100%;
  height: 180px;
  background: #f8f6f7;
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
  border-top-left-radius: 18px;
  border-top-right-radius: 18px;
  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.22s;
  }
}
.project-card:hover .project-image img {
  transform: scale(1.08);
}
.project-info {
  padding: 18px 20px 18px 20px;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.project-name {
  font-size: 1.18rem;
  font-weight: 700;
  font-family: 'Brandon', Arial, sans-serif;
  margin-bottom: 6px;
  color: #FC3A79;
}
.project-description {
  font-size: 1rem;
  font-family: 'Bricolage', Arial, sans-serif;
  color: #261F22;
  margin-bottom: 14px;
}
.project-links {
  display: flex;
  flex-direction: row;
  gap: 18px;
  a.project-link {
    font-size: 1rem;
    font-family: 'Neue Montreal', Arial, sans-serif;
    color: #FE572E;
    font-weight: 600;
    text-decoration: none;
    display: flex;
    align-items: center;
    gap: 4px;
    background: rgba(252, 58, 121, 0.07);
    padding: 6px 16px;
    border-radius: 18px;
    transition: background 0.18s, color 0.18s, transform 0.18s;
  }
  a.project-link:hover {
    background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
    color: #fff;
    transform: translateY(-2px) scale(1.06);
  }
  a.project-link img {
    width: 16px;
    height: 16px;
    margin-left: 2px;
  }
}
@media (max-width: 900px) {
  .project-landing {
    padding: 0 4px;
  }
  .project-list {
    gap: 18px;
  }
  .project-card {
    width: 100%;
    min-width: 0;
  }
}
@media (max-width: 600px) {
  .project-landing {
    padding-left: 8px;
    padding-right: 8px;
  }
  .project-landing-title {
    font-size: 1.3rem;
    margin-bottom: 28px;
  }
  .category-title {
    font-size: 1.1rem;
  }
  .category-header {
    gap: 10px;
    margin-bottom: 10px;
  }
  .project-list {
    gap: 10px;
  }
  .project-card {
    width: 100%;
    min-width: 0;
    border-radius: 12px;
    margin-bottom: 16px;
  }
  .project-image {
    height: 120px;
    border-top-left-radius: 12px;
    border-top-right-radius: 12px;
  }
  .project-info {
    padding: 10px 10px 12px 10px;
  }
  .project-name {
    font-size: 1rem;
  }
  .project-description {
    font-size: 0.92rem;
  }
  .project-links a.project-link {
    font-size: 0.92rem;
    padding: 5px 10px;
    border-radius: 12px;
  }
  .project-links a.project-link img {
    width: 13px;
    height: 13px;
  }
}
</style>
