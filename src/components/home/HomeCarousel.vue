<template>
    <el-container class="page-header darken-filter" :style="{ backgroundImage: `url(${src})` }">
        <el-row class="content-header">
            <p class="title1"> {{ title1 }} </p>
            <p class="subtitle1"> {{ subtitle1 }} </p>
        </el-row>
        <el-row class="content-header-2">
            <p class="title2"> {{ title2 }} </p>
            <p class="opcao"> {{ opcao1 }} </p>
            <p class="opcao"> {{ opcao2 }} </p>
            <p class="opcao"> {{ opcao3 }} </p>
        </el-row>
    </el-container>
</template>

<style lang="scss">
@import '../../styles/variables.scss';

    .page-header {
        height: 100vh;
        background-repeat:no-repeat;
        background-position: center top;
        background-size: cover;
        background-attachment: fixed;
        padding-top: 300px;
        padding-bottom: 300px;

        flex-direction: column;

        .content-header {
            display: flex;
            text-align: center;
            justify-content: center;
            align-items: center;
            flex-direction: column;
                
            .title1 {
                font: Bold 100px/133px Segoe UI;
                margin: 0;
                color: #FFFFFF;
                opacity: 1;
                z-index: 2;
            }
            .subtitle1 {
                font: Bold 35px/47px Segoe UI;
                letter-spacing: 0;
                margin: 0;
                color: #FCF9F9;
                opacity: 1;
                z-index: 2;
            }
        }  
        .content-header-2 {
            padding-top: 370px;
            display: flex;
            text-align: center;
            justify-content: center;
            align-items: center;
            flex-direction: column;

                
            .title2 {
                font: Bold 50px/67px Segoe UI;
                letter-spacing: 0;
                margin: 0;
                color: #FFFFFF;
                opacity: 1;
                z-index: 2;
                padding-bottom: 40px;
            }
            .opcao {
                font: Bold 30px Segoe UI;
                padding-top: 20px;
                letter-spacing: 0;
                margin: 0;
                color: #FCF9F9;
                opacity: 1;
                z-index: 2;
            }
        }   
    }
</style>

<script>

export default {
    name: 'PageHeader',
    data() {
        return {
            src: require('@/assets/atenas.png'),

            title1: 'Grécia Antiga',
            subtitle1: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit',

            title2: 'Como vai funcionar?',
            opcao1: '- Uma videoaula sobre a Grécia antiga',
            opcao2: '- Um questionário com 3 perguntas sobre',
            opcao3: '- Seu resultado na hora',
        }
    }
}
</script>