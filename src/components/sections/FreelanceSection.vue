<template>
  <section class="freelance-section">
    <div class="freelance-card fade-in">
      <div class="freelance-accent"></div>
      <h2 class="title">Let’s work together.</h2>
      <p class="subtitle">
        Open for freelance design projects.<br>
        Simple, fast, and beautiful results—let’s connect!
      </p>
      <div class="contact-container">
        <button class="contact-btn email-btn" @click="copyToClipboard('workwithriny@gmail.com', 'Email')">
          <img src="../../assets/icons/quality.svg" alt="Email" class="contact-icon" />
          Email me
        </button>
        <button class="contact-btn phone-btn" @click="copyToClipboard('+916393103784', 'Phone Number')">
          <img src="../../assets/icons/phone.svg" alt="Phone" class="contact-icon" />
          Call me
        </button>
      </div>
      <button class="connect" @click="sendMail()">
        <img src="../../assets/icons/rocket.svg" alt="Rocket" class="connect-icon" />
        Start your project
      </button>
    </div>
  </section>
</template>

<script>
export default {
  name: "FreelanceSection",
  methods: {
    copyToClipboard(text, textType) {
      navigator.permissions.query({ name: "clipboard-write" }).then((result) => {
        if (result.state == "granted" || result.state == "prompt") {
          navigator.clipboard
            .writeText(text)
            .then(() => this.$message({ message: textType + " Copied", type: "success" }))
            .catch(() => console.log("failure"));
        }
      });
    },
    sendMail() {
      let emailTo = "workwithriny@gmail.com";
      let emailString = "mailto:" + emailTo;
      window.location.href = emailString;
    },
  },
};
</script>

<style scoped>
.freelance-section {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 420px;
  margin: 80px 0 60px 0;
  position: relative;
  z-index: 1;
}

.freelance-card {
  position: relative;
  background: rgba(255,255,255,0.55);
  border-radius: 32px;
  box-shadow: 0 8px 32px rgba(252, 58, 121, 0.10), 0 2px 12px rgba(0,0,0,0.08);
  backdrop-filter: blur(16px);
  padding: 56px 64px 48px 64px;
  max-width: 900px;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow: visible;
  animation: fadeUp 0.8s cubic-bezier(.4,2,.6,1) both;
}

.freelance-accent {
  position: absolute;
  top: -60px;
  left: 50%;
  transform: translateX(-50%);
  width: 220px;
  height: 90px;
  background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
  opacity: 0.15;
  filter: blur(36px);
  border-radius: 50%;
  z-index: 0;
  animation: accentFloat 5s ease-in-out infinite alternate;
}

@keyframes accentFloat {
  0% { transform: translateX(-50%) scale(1) }
  100% { transform: translateX(-50%) scale(1.12) }
}

.title {
  font-family: Brandon, sans-serif;
  font-size: 2.5rem;
  font-weight: 500;
  color: #261F22;
  margin-bottom: 12px;
  letter-spacing: 0.5px;
  text-align: center;
  z-index: 1;
}

.subtitle {
  font-family: Bricolage, sans-serif;
  font-size: 1.25rem;
  color: #555;
  margin-bottom: 28px;
  text-align: center;
  font-weight: 400;
  z-index: 1;
}

.contact-container {
  display: flex;
  flex-direction: row;
  gap: 28px;
  margin-bottom: 32px;
  z-index: 1;
}

.contact-btn {
  display: flex;
  align-items: center;
  gap: 10px;
  border: none;
  border-radius: 14px;
  padding: 18px 38px;
  font-family: Bricolage, monospace;
  font-size: 1.08rem;
  font-weight: 500;
  background: #fff;
  color: #FC3A79;
  box-shadow: 0 2px 8px rgba(252, 58, 121, 0.08);
  cursor: pointer;
  transition: background 0.22s, color 0.22s, transform 0.22s;
  outline: none;
  position: relative;
  z-index: 1;
}
.contact-btn:hover {
  background: #FC3A79;
  color: #fff;
  transform: translateY(-2px) scale(1.04);
}
.email-btn .contact-icon,
.phone-btn .contact-icon,
.contact-icon {
  width: 22px;
  height: 22px;
  /* #FC3A79 filter */
  filter: brightness(0) saturate(100%) sepia(1) hue-rotate(-30deg) saturate(6);
  transition: filter 0.22s;
}
.contact-btn:hover .contact-icon {
  /* white */
  filter: brightness(0) invert(1);
}

.connect {
  margin-top: 18px;
  padding: 22px 64px;
  border-radius: 100px;
  border: none;
  background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
  color: #fff;
  font-family: Bricolage, sans-serif;
  font-size: 1.25rem;
  font-weight: 600;
  letter-spacing: 1px;
  box-shadow: 0 4px 24px rgba(252, 58, 121, 0.10), 0 1.5px 6px rgba(0,0,0,0.07);
  display: flex;
  align-items: center;
  gap: 12px;
  cursor: pointer;
  transition: background 0.22s, transform 0.22s;
  z-index: 1;
  animation: fadeUp 0.9s cubic-bezier(.4,2,.6,1) both;
}
.connect:hover {
  background: linear-gradient(90deg, #FE572E 0%, #FC3A79 100%);
  transform: translateY(-2px) scale(1.04);
}
.connect-icon {
  width: 26px;
  height: 26px;
  margin-right: 2px;
  /* always white to match .connect text */
  filter: brightness(0) invert(1) drop-shadow(0 2px 6px rgba(252, 58, 121, 0.10));
  transition: filter 0.22s;
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
  .freelance-card {
    padding: 28px 8px 24px 8px;
    border-radius: 18px;
    max-width: 98vw;
  }
  .contact-container {
    flex-direction: column;
    gap: 12px;
    margin-bottom: 18px;
  }
  .connect {
    font-size: 1rem;
    padding: 14px 18px;
    border-radius: 60px;
  }
  .title {
    font-size: 1.2rem;
    margin-bottom: 10px;
  }
  .subtitle {
    font-size: 0.98rem;
    margin-bottom: 18px;
  }
}
</style>
