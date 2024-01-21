<template>
    <div class="footer-section">
        <div class="social-section">
            <img src="../../assets/icons/dribble-icon.png" alt="Dribble Icon" class="social-icon" />
            <img src="../../assets/icons/linkedin-icon.png" alt="LinkedIn Icon" class="social-icon" />
            <img src="../../assets/icons/behance-icon.png" alt="Behance Icon" class="social-icon" />
        </div>
        <el-row class="policy-and-terms-section">
            <el-col :span="12">
                <span class="policy-and-terms">Privacy Policy</span>
            </el-col>
            <el-col :span="12">
                <span class="policy-and-terms">Terms of Use</span>
            </el-col>
            <el-col :span="24" class="rights">
                © 2024 Riny Yadav. All rights reserved.
            </el-col>
        </el-row>
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
.policy-and-terms-section {
    display: flex;
    justify-content: center;
    align-items: center;
    width: auto;
    min-width: 300px;
    margin: 35px 0;

    color: var(--Black, #261F22);
    font-family: "Brandon";
    font-size: 16px;
    font-style: normal;
    font-weight: 600;
    line-height: 24px;
}
.rights {
    cursor: pointer;
    color: var(--black75, rgba(38, 31, 34, 0.75));
    font-family: "Brandon";
    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: 24px;
    margin-top: 20px;
}
</style>