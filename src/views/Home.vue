<template>
    <el-row>
        <Navbar style="z-index: 99"></Navbar>
        <HomeCarousel />
        <el-row>
            <Presentation />
            <Quiz />
        </el-row>
        <Footer />
    </el-row>
</template>

<style lang="scss" scoped>
@import "../styles/variables.scss";

</style>

<script>
import Navbar from "../components/home/Navbar.vue";
import HomeCarousel from "../components/home/HomeCarousel.vue";
import Presentation from "../components/home/Presentation.vue";
import Quiz from "../components/home/Quiz.vue";
import Footer from "../components/home/Footer.vue";

export default {
    name: "Home",
    components: {
        Navbar,
        HomeCarousel,
        Presentation,
        Quiz,
        Footer
    }
}
</script>