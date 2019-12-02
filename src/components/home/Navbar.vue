<template>
  <el-menu class="el-menu-demo" mode="horizontal" background-color="#10ADB2" text-color="#fff" justify="center">
    <el-image class="logo-image" :src="img" @click="scrollTo()"></el-image>
    <el-menu-item class="botao-nav"><a href="/#pesentationSection">Vídeo Aula</a></el-menu-item>
    <el-menu-item class="botao-nav"><a href="/#quizSection">Questionário</a></el-menu-item>
  </el-menu>
</template>

<style lang="scss" scoped>
el-menu{
  height: 70px;
}

.logo-image{
  position: absolute;
  height: 40px;
  width: 40px;
  top: 10px;
  left: 20px;
  cursor: pointer;
  z-index: 1;
}

.logo-image:hover
{
  -webkit-transform: scale(0.8);
  -ms-transform: scale(0.8);
  transform: scale(0.8);
}
.el-menu-demo{
  z-index: 3;
  width: 100%;
  position: fixed;
  display: flex;
  flex-direction: row;
  justify-content: center;
  border-bottom: 0 !important;
  font-weight: bold;
}

.bota-nav {
  z-index: 1 !important;
  background-color: transparent !important;
  color: white; 
}

.botao-nav:hover{
  background-color: rgb(0, 130, 134) !important;
}

</style>


<script>
  export default {
    data() {
      return {
        img: require('@/assets/museum.png'),
      };
    },
    methods: {
       scrollTo() {
        if(window.location.href == "http://localhost:8080"){
          window.location.href = "http://localhost:8080";
        }
        window.scroll({
          behavior: 'smooth',
          top: 0
        });
      },
    },
  }
</script>