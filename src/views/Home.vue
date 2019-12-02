<template>
    <el-row>
        <HomeCarousel />
        <Presentation />
    </el-row>
</template>

<style lang="scss" scoped>
@import "../styles/variables.scss";

</style>

<script>
import HomeCarousel from "../components/home/HomeCarousel.vue";
import Presentation from "../components/home/Presentation.vue";

export default {
    name: "Home",
    components: {
        HomeCarousel,
        Presentation,
    }
}
</script>