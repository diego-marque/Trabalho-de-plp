<template>
    <el-row class="max-width-container">
        <HomeCarousel />
        <Presentation />
        <Quiz />
    </el-row>
</template>

<style lang="scss" scoped>
@import "../styles/variables.scss";

</style>

<script>
import HomeCarousel from "../components/home/HomeCarousel.vue";
import Presentation from "../components/home/Presentation.vue";
import Quiz from "../components/home/Quiz.vue";

export default {
    name: "Home",
    components: {
        HomeCarousel,
        Presentation,
        Quiz,
    }
}
</script>