<template>
    <el-row class="max-width-container">
        <Navbar />
        <HomeCarousel />
        <Presentation />
        <Quiz />
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

export default {
    name: "Home",
    components: {
        Navbar,
        HomeCarousel,
        Presentation,
        Quiz,
    }
}
</script>