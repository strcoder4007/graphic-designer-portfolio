<template>
  <footer class="footer-section">
    <div class="footer-content">
      <div class="footer-links-row">
        <a class="footer-link" href="/" aria-label="Home">Home</a>
        <a class="footer-link" href="/about" aria-label="About">About</a>
        <a class="footer-link" href="/work" aria-label="Work">Work</a>
        <a class="footer-link" href="/contact" aria-label="Contact">Contact</a>
        <a class="footer-link" href="https://strcoder4007.github.io/graphic-designer-portfolio/resume.pdf" target="_blank" aria-label="Resume">Resume</a>
      </div>
      <div class="footer-social">
        <a href="https://dribbble.com/rinydesigns" target="_blank" aria-label="Dribbble">
          <img src="../../assets/icons/dribble-icon-colored.svg" alt="Dribbble Icon" />
        </a>
        <a href="https://www.linkedin.com/in/riny-yadav-a24a90238/" target="_blank" aria-label="LinkedIn">
          <img src="../../assets/icons/linkedin-icon-colored.svg" alt="LinkedIn Icon" />
        </a>
        <a href="https://www.behance.net/rinyyadav" target="_blank" aria-label="Behance">
          <img src="../../assets/icons/behance-icon-colored.svg" alt="Behance Icon" />
        </a>
      </div>
      <div class="footer-tagline">
        <span>Designed by me<span class="footer-heart">♥</span></span>
      </div>
      <div class="footer-divider"></div>
      <div class="footer-copyright">
        © 2025 Riny Yadav. All rights reserved.
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "FooterSection",
};
</script>

<style scoped>
.footer-section {
  width: 100%;
  background: transparent;
  padding: 48px 0 18px 0;
  margin: 0;
  border-top: none;
  display: flex;
  justify-content: center;
  align-items: center;
  box-shadow: 0 -2px 24px 0px rgba(252, 58, 121, 0.08);
  border-top-left-radius: 48px;
  border-top-right-radius: 48px;
  overflow: hidden;
}
.footer-content {
  width: 100%;
  max-width: 1100px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 18px;
}
.footer-links-row {
  display: flex;
  flex-direction: row;
  gap: 32px;
  margin-bottom: 10px;
  flex-wrap: wrap;
  justify-content: center;
}
.footer-link {
  font-family: 'Neue Montreal', 'Brandon', Arial, sans-serif;
  font-size: 1.08rem;
  color: #FC3A79;
  text-decoration: none;
  padding: 8px 18px;
  border-radius: 24px;
  background: rgba(252, 58, 121, 0.07);
  transition: background 0.18s, color 0.18s, transform 0.18s;
  font-weight: 600;
  letter-spacing: 0.2px;
  margin: 2px 0;
}
.footer-link:hover {
  background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
  color: #fff;
  transform: translateY(-2px) scale(1.06);
}
.footer-social {
  display: flex;
  flex-direction: row;
  gap: 28px;
  margin-bottom: 8px;
  a {
    display: flex;
    align-items: center;
    justify-content: center;
    transition: transform 0.18s;
    border-radius: 50%;
    background: none;
    &:hover {
      transform: scale(1.18);
      background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
    }
    img {
      width: 32px;
      height: 32px;
      display: block;
      transition: filter 0.18s;
      filter: grayscale(0) brightness(1);
    }
    &:hover img {
      filter: brightness(0) invert(1);
    }
  }
}
.footer-tagline {
  font-family: 'Neue Montreal', 'Brandon', Arial, sans-serif;
  font-size: 1.08rem;
  color: #261F22;
  opacity: 0.85;
  margin-bottom: 4px;
  .footer-heart {
    color: #FC3A79;
    font-size: 1.15em;
    font-weight: bold;
    vertical-align: middle;
    margin: 0 2px;
  }
}
.footer-divider {
  width: 100%;
  height: 1.5px;
  background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
  opacity: 0.18;
  border-radius: 1px;
  margin: 0 0 8px 0;
}
.footer-copyright {
  font-family: 'Neue Montreal', 'Brandon', Arial, sans-serif;
  font-size: 1.08rem;
  color: #261F22;
  text-align: center;
  opacity: 0.85;
  letter-spacing: 0.2px;
}
@media (max-width: 900px) {
  .footer-section {
    padding: 32px 0 12px 0;
    border-top-left-radius: 32px;
    border-top-right-radius: 32px;
  }
  .footer-content {
    gap: 14px;
  }
  .footer-links-row {
    gap: 18px;
    font-size: 0.98rem;
  }
  .footer-social {
    gap: 16px;
    a img {
      width: 24px;
      height: 24px;
    }
  }
  .footer-tagline,
  .footer-copyright {
    font-size: 0.98rem;
  }
}
@media (max-width: 600px) {
  .footer-section {
    padding: 18px 0 8px 0;
    border-top-left-radius: 18px;
    border-top-right-radius: 18px;
  }
  .footer-content {
    gap: 10px;
  }
  .footer-links-row {
    gap: 10px;
    font-size: 0.92rem;
  }
  .footer-social {
    gap: 10px;
    a img {
      width: 18px;
      height: 18px;
    }
  }
  .footer-tagline,
  .footer-copyright {
    font-size: 0.92rem;
  }
}
</style>
