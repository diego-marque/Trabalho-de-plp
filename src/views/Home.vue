<template>
    <el-row>
        <HomeCarousel />
    </el-row>
</template>

<style lang="scss" scoped>
@import "../styles/variables.scss";

</style>

<script>
import HomeCarousel from "../components/home/HomeCarousel.vue";

export default {
    name: "Home",
    components: {
        HomeCarousel,
    }
}
</script>