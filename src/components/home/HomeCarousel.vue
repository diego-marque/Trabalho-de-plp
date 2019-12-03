<template>
    <el-carousel id="homeCarousel" class="home-carousel" trigger="click" arrow="never" height="100vh">
            <el-carousel-item v-for="item in items" :key="item.id">
                <el-row class="darken-filter" :style="{ backgroundImage: `url(${item.photo})` }">
                    <el-col align="center" class="carousel-item-content">
                        <h1><b>{{ item.firstWord[0] }}</b>{{ item.title }}</h1>
                        <p class="description" v-if="item.id = 1">{{ item.description }}</p>
                        <div class="div-itens">
                            <p class="itens"> {{ item.item1 }} </p>
                            <p class="itens"> {{ item.item2 }} </p>
                            <p class="itens"> {{ item.item3 }} </p>
                        </div>
                    </el-col>
                </el-row>
            </el-carousel-item>
    </el-carousel>
</template>

<style lang="scss">
    .home-carousel {

        .el-carousel__item{
            
                .el-row {
                    background-repeat: no-repeat;
                    background-size: cover;
                }            
            }

            .el-carousel__indicators {
                bottom: 4% !important;

                .is-active {

                    .el-carousel__button {
                        background-color: white !important;
                    }
                }

                .el-carousel__button {
                    height: 20px !important;
                    width: 20px !important;
                    border-radius: 50px;
                    background-color: transparent !important;
                    opacity: 1 !important;
                    border: 3px solid rgba(255, 255, 255, 1) !important;
                }
            }

            .carousel-item-content {
                display: flex;
                justify-content: center;
                flex-direction: column;
                align-items: center;
                z-index: 2 !important;
                height: 100vh;
                h1 {
                    font-size: 6.7em;
                    font-weight: 100;
                    margin: 0;
                    width: 90%;

                    b {
                        font-weight: bold;
                    }
                }

                .description {
                    font-size: 28px;
                    width: 100%;
                }

                .div-itens {
                    text-align: left;

                    .itens {
                        font-size: 28px;
                        width: 100%;
                    }
                }

            }

            @media only screen and (max-width: 1024px) {
                .carousel-item-content {

                    .description {
                        width: 80%;
                    }

                    .div-itens {

                        .itens {
                            font-size: 28px;
                        }
                    }
                }
            }

            @media only screen and (max-width: 600px) {
                .carousel-item-content {

                    h1 {
                        width: 93%;
                        font-size: 2.5em;
                    }

                   .description {
                        font-size: 1.5em;
                        margin-bottom: 0px;
                    }

                    .div-itens {
                        margin-top: 0px;
                        text-align: center;
                        .itens {
                            font-size: 1.0em;
                        }
                    }
                }
            }
    }
</style>

<script>
export default {
    name: 'HomeCarousel',
    data() {
        return {
            items: [
                {
                    id: 1,
                    photo: require('@/assets/atenas.png'),
                    title: "GRÉCIA ANTIGA",
                    description: "Módulo 1: período Clássico",
                    created_at: "2019-07-30 02:17:30",
                    updated_at: "2019-07-30 02:17:35"
                },
                {
                    id: 2,
                    photo: require('@/assets/estatuas.jpg'),
                    title: "Como vai funcionar?",
                    item1: "- Uma videoaula sobre a Grécia antiga",
                    item2: "- Um questionário com 3 perguntas sobre",
                    item3: "- Seu resultado na hora!",
                    created_at: "2019-08-06 21:27:47",
                    updated_at: "2019-08-06 21:27:55"
                },
            ],
        }
    },
    beforeMount() {
        this.items = this.items.map(item => {
            item.firstWord = item.title.split(' ', 1);
            item.title = item.title.replace(item.firstWord, '');
            return item;
        });
    },
    components: {
    }
}
</script>
