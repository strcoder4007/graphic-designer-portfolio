<template>
    <div class="footer-section">
        <div class="social-section">
            <img src="../assets/icons/dribble-icon.png" alt="Dribble Icon" class="social-icon" />
            <img src="../assets/icons/linkedin-icon.png" alt="LinkedIn Icon" class="social-icon" />
            <img src="../assets/icons/behance-icon.png" alt="Behance Icon" class="social-icon" />
        </div>
        <div class="policy-and-terms-section">

        </div>
        <span>
            © 2024 Riny Yadav. All rights reserved.
        </span>
    </div>
</template>
<script>
    export default {
        name: "FooterSection",
    };
</script>
<style scoped>
.footer-section {
    height: auto;
    max-height: 600px;
    min-height: 300px;
    background: transparent;
    backdrop-filter: blur(2px);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    border-top: 1px solid #261F221A;
}
</style>