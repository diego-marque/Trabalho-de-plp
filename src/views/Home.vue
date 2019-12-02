<template>
    <el-row>
        <Navbar />
        <HomeCarousel />
        <Presentation id="PresentationSection"/>
    </el-row>
</template>

<style lang="scss" scoped>
@import "../styles/variables.scss";

</style>

<script>
import Navbar from "../components/home/Navbar.vue";
import HomeCarousel from "../components/home/HomeCarousel.vue";
import Presentation from "../components/home/Presentation.vue";
export default {
    name: "Home",
    components: {
        Navbar,
        HomeCarousel,
        Presentation,
    }
}
</script>