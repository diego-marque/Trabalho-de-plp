<template>
    <el-row justify="center" class="presentation-container">
        <el-main>
            <el-col class="youtube-video" align="center" :sm="24" :md="12">
                <youtube id="youtube-video" :video-id="presentationVideo.video_id" :mute="true" @ready="ready"></youtube>
            </el-col>
            <el-col class="presentation-video-description" :sm="24" :md="12">
                <h1>Grécia Antiga, módulo I: período clássico</h1>
                <p id="text-presentation"> {{presentationVideo.description}} </p>
            </el-col>
        </el-main>
    </el-row>
</template>

<style lang="scss">
    @import '../../styles/variables.scss';
    
    @keyframes fadeIn {
        from {
        opacity: 0;
        }
        to{
            opacity: 1;
        }
    }
    @-moz-keyframes fadeIn {
        from {
        opacity: 0;
        }
        to{
        opacity: 1;
         }
    }
    @-webkit-keyframes fadeIn {
        from {
        opacity: 0;
        }
        to{
            opacity: 1;
        }
    }
    .efeito-text{
        animation-iteration-count: 1;
        -moz-animation: fadeIn 2s ease-out !important;
        animation: fadeIn 2s ease-out !important;
        -webkit-animation: fadeIn 2s ease-out !important;
    }
    .presentation-container {
        padding: 5%;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
        min-height: 50vh;
        background: #10ADB2;
        

        .el-main {
            max-width: $container-max-width;
            display: flex;
            flex-wrap: wrap;
            padding-top: 3%; 
            padding-bottom: 3%;
        }

        .presentation-video-description {
            padding: 0 5% 0 5%;

            h1 {
                font: Bold 40px Segoe UI;
                color: #ECEAEA;
                margin: 0;
            }

            p {
               font: 20px Segoe UI;
            }
        }

        .youtube-video {

            #youtube-video {
                display: flex;
                align-items: center;

                iframe {
                    display: flex;
                    width: 100%;
                }    
            }
        }

        @media screen and (max-width: 1024px) {
            .el-main {
                padding-top: 8%; 
                padding-bottom: 8%;
            }

            .presentation-video-description {

                h1 {
                    font-size: 2.0em;
                    text-align: left;                }

                p {
                    font-size: 1.2em;
                    text-align: left;
                }
            } 
        }

        @media screen and (max-width: 768px) {
            .presentation-video-description {
                
                h1 {
                    margin-top: 30px;
                    font-size: 2.0em;
                    text-align: left;                }

                p {
                    font-size: 1.1em;
                    text-align: left;
                }
            } 
        }
    }
</style>

<script>
import Vue from 'vue'
import _ from 'lodash'
import VueYoutubeEmbed from 'vue-youtube-embed'

Vue.use(VueYoutubeEmbed)

export default {
    name: 'Presentation',
    data() {
        return {
            presentationVideo: {
                video_id: "0sVur4PJjcw",
                video_url: "https://www.youtube.com/watch?v=0sVur4PJjcw",
                description: "O presente módulo apresentará as principais fases do período clássico grego, entre os anos de 500 a 338 a.C., dominado pelas poleis de Esparta e Atenas. Na vídeo-aula de hoje explicaremos os motivos que ocasionaram as Guerras Médicas e a formação da Liga do Peloponeso por Esparta e a Liga de Delos por Atenas, além de explicitar o florescimento científico e filosófico do mundo Grego no período Clássico."
            },
            player: {},
            ytComponent: {},
        }
    },
    methods: {
        ready(event) {
            this.player = event.target;
        },
        handleScroll() {
            const ytComponentBounding = this.ytComponent.getBoundingClientRect();
            if(ytComponentBounding.top < window.innerHeight)
                this.player.playVideo();
            if(ytComponentBounding.top >= window.innerHeight || ytComponentBounding.top + ytComponentBounding.height <= 0)
                this.player.pauseVideo();
        }
    },
    created() {    
        this.debouncedScroll = _.debounce(this.handleScroll, 150);
        window.addEventListener('scroll', this.debouncedScroll);   
    },
    mounted() {
        this.ytComponent = document.querySelector('.youtube-video');      

        window.addEventListener('scroll', () => {
            const scrolled = window.scrollY;
            const position = document.getElementById("text-presentation").offsetTop;
            if(scrolled >=position){
                setEfect();
            }
        });

    },
    beforeDestroy() {
        window.removeEventListener('scroll', this.debouncedScroll);
    }
}
function setEfect(){
    document.getElementById("text-presentation").className = "efeito-text";
}
</script>