<template>
  <el-menu 
  id="el-menu-horizontal-demo" 
  text-color="#ffffff"
  active-text-color="#ffffff"
  :router="true">
    <!--TOGLE COM ITENS-->
    <el-image class="logo-image" @click="scrollTo()" :src="img" ></el-image>
    <el-container v-show="toggle == true">
      <el-header style="text-align: right" class="menu-nav-toggle">
        <el-dropdown trigger="click">
          <font-awesome-icon class="toggle-buttom" icon="align-justify" size="2x"></font-awesome-icon>
          <el-dropdown-menu slot="dropdown" class="menu-dropdown">
            <el-dropdown-item class="item-navbar"><a href="/#pesentationSection">Vídeo Aula</a></el-dropdown-item>
            <el-dropdown-item class="item-navbar"><a href="/#quizSection">Questionário</a></el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
      </el-header>
    </el-container>
    <!--ITENS-NORMAIS-->
    <el-container class="menu-nav-horizontal" v-show="toggle == false">
      <el-menu-item class="item-navbar"><a href="/#pesentationSection">Vídeo Aula</a></el-menu-item>
      <el-menu-item class="item-navbar"><a href="/#quizSection">Questionário</a></el-menu-item>
    </el-container>
  </el-menu> 
</template>

<style lang="scss" scoped>
  #el-menu-horizontal-demo{
    top: 0;
    width: 100vw;
    position: fixed;
    height: 75px;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    border-bottom: solid 1px transparent;
    background-color: transparent;
    align-items: center;
    justify-content: vertical;
  }
  .logo-image{  
    position: absolute !important;
    left: 25px !important;
    top: 10px !important;
    height: 50px !important;
    width: 50px !important;
    cursor: pointer;
  }
  .logo-image:hover{
    -webkit-transform: scale(0.8);
    -ms-transform: scale(0.8);
    transform: scale(0.8);
  }
  .menu-nav-toggle{
    width: 100vw !important;
  }

  .toggle-buttom{
    color: white;
    cursor : pointer;
    margin-top: 20px;
  }
  .el-dropdown-menu.el-popper{
    background-color: #282728;
    right: 0 !important;
    left: 60% !important;
    top: 0;
  }
  .menu-nav-horizontal{
    display: flex;
    align-items: center;
    justify-content: horizontal;
    a{
      color: white !important;
      text-decoration: none;	
    }
  }
  .item-navbar{
    z-index: 1 !important;
    font-size: 23px !important;
    background-color: transparent !important;
    color: white;
    
  }
  .item-navbar:hover{
    background-color: transparent !important;
    color: white !important;
    position: relative;
  }
  .item-navbar:focus{
    font-weight: bold;
  }
  .el-dropdown-menu__item{
      width: -moz-max-content !important;
      width: -webkit-max-content !important;
  }
  .item-navbar:hover::before{  
    content: '' !important;
    background-color: #10ADB2 !important;
    width: 90% !important;
    height: 17% !important;
    position: absolute !important;
    z-index: -1 !important;
    top: 60% !important;
    left: 5% !important;
    -moz-animation: slideInMenu .2s ease-out !important;
    animation: slideInMenu .2s ease-out !important;
    -webkit-animation: slideInMenu .2s ease-out !important;
  }
  @keyframes slideInMenu {
    from {
      transform: translateX(-15px);
    }
    to{
      transform: translateX(0px);
    }
  }
  @-moz-keyframes slideInMenu {
    from {
      transform: translateX(-15px)
    }
    to {
      transform: translateX(15px)
    }
  }
  @-webkit-keyframes slideInMenu {
    from {
      transform: translateX(-15px)
    }
    to {
      transform: translateX(15px)
    }
  }
  @media screen and (max-width:1279px) and (min-width: 769px){
    .item-navbar:hover::before{ 
      content: '' !important;
      background-color: #c42661 !important;
      width: 90% !important;
      height: 25% !important;
      position: absolute !important;
      z-index: -1 !important;
      top: 60% !important;
    }
    .item-navbar{ 
      padding: 10px !important;
    }
    #el-menu-horizontal-demo{
      height: 60px;
    }
    .logo-image{
      height: 40px !important;
      width: 40px !important;
    }
  }
  @media screen and (max-width: 768px){
    .item-navbar{
      font-size: 15px !important;
    }
    #el-menu-horizontal-demo{
      display: flex;
      align-items: center;
      height: 70px;
    }
    .logo-image{
      margin-top: 2px;
      height: 40px !important;
      width: 40px !important;
    }
    .toggle-buttom{
      margin-right: 10px;
    }
  }
  @media screen and(max-width: 414px){
    #el-menu-horizontal-demo{
      height: 40px;
    }
    .logo-image{
      height: 25px !important;
      width: 25px !important;
    }
    #el-menu-horizontal-demo{
      padding: 2% 0 2% 0 !important;
    }
    .toggle-buttom{
      margin-top: 25px;
      margin-right: 0px;
    }
  }

</style>

<script>
export default {
  name: 'Navbar',
  data(){
    return {
      img: require('@/assets/museum.png'),
      toggle: false,
      menuVertical: false,
    }
  },
  methods :{
    setVertical(){
      this.menuVertical = true;
    },
    setHorizontal(){
      this.menuVertical = false;
    },
    setMode(){
        if (window.innerWidth < 1280) {
          this.toggle = true;
        }else{
          this.toggle = false;
        }
    },
     scrollTo() {
        document.getElementById("homeCarousel").scrollIntoView();
    },
    changeColorNav(condicao) {
        if(condicao == "setColor"){
          document.getElementById("el-menu-horizontal-demo").style.backgroundColor="#282728"
        }else{
          document.getElementById("el-menu-horizontal-demo").style.backgroundColor="transparent"
        }
    }
  },
   created() {
       window.addEventListener('resize', this.setMode);
       this.setMode()
   },
   beforeDestroy() {
       window.removeEventListener('resize', this.setMode);
       window.removeEventListener('scroll');
   },
   mounted(){
     window.addEventListener('scroll', () => {
       const scrolled = window.scrollY;
       const firstDiv = document.getElementById("homeCarousel").offsetHeight;
       if(scrolled >= firstDiv){
         this.changeColorNav("setColor");
       }else{
         this.changeColorNav("notSetColor")
       }
      });
   },
}
</script>