<template>
    <div class="tools-section">
        <span class="title">Tools I use</span>
        <el-row>
            <el-col :span="6">Adobe Firefly</el-col>
            <el-col :span="6">Figma</el-col>
            <el-col :span="6">Adobe Photoshop</el-col>
            <el-col :span="6">Adobe Illustrator</el-col>
        </el-row>
    </div>
</template>
<script>
    export default {
        name: "ToolsSection",
        methods: {}
    };
</script>
<style scoped>
.tools-section {
    height: auto;
    max-height: 600px;
    min-height: 200px;
    background: transparent;
    backdrop-filter: blur(2px);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: start;
    margin: 10px 150px 20px 150px;
    .title {
        display: block;
        color: var(--Black, #261F22);
        font-family: Brandon;
        font-size: 36px;
        font-style: normal;
        font-weight: 700;
        line-height: 48px;
        text-align: left;
        margin-bottom: 20px;
    }
}

@media (max-width: 768px) {
    .tools-section {
        margin: 60px 30px 50px 30px;
        min-height: 100px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: baseline;
        .title {
            font-size: 30px;
            line-height: 30px;
        }
    }
}
</style>