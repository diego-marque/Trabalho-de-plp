<template>
    <el-container id="quizSection" class="container">
        <el-row>
            <h2 class="texto">Acesse o questionário assim que finalizar a videoaula.</h2>
        </el-row>
        <el-row>
            <el-button class="button-style" flat @click="dialog = true">JÁ ASSISTI AO VÍDEO</el-button>
        </el-row>
        <el-dialog title="Questionário" :visible.sync="dialog" @closed="close()">
            <el-form :model="editedItem" :rules="rules" class="form demo-ruleForm">
                <h3 style="margin: 0">1. Qual dessas cidades da antiguidade eram consideradas poleis gregas? "</h3>
                <input type="radio" id="one" value="a" v-model="editedItem.question1">
                <label for="one">a) Ur.</label>
                <br>
                <input type="radio" id="one" value="b" v-model="editedItem.question1">
                <label for="two">b) Roma.</label>
                <br>
                <input type="radio" id="one" value="c" v-model="editedItem.question1">
                <label for="three">c) Cartago.</label>
                <br>
                <input type="radio" id="one" value="d" v-model="editedItem.question1">
                <label for="four">d) Esparta.</label>
                <br>
                <input type="radio" id="one" value="e" v-model="editedItem.question1">
                <label for="five">e) Vaticano.</label>
                <br>
                <br>
                <br>
                <h3 style="margin: 0">2. De acordo com a vídeo-aula apresentada acima, assinale a alternativa que corresponde a manifestações que ocorreram no período clássico: "</h3>
                <input type="radio" id="one" value="a" v-model="editedItem.question2">
                <label for="one">a) Surgimento dos jogos olímpicos como uma forma de manifestação religiosa e experiência atlética, além da competição entre as cidades-estado da região.</label>
                <br>
                <input type="radio" id="one" value="b" v-model="editedItem.question2">
                <label for="two">b) Aparecimento da civilização Minoica, durante a Idade do Bronze grega, na região de Creta.</label>
                <br>
                <input type="radio" id="one" value="c" v-model="editedItem.question2">
                <label for="three">c) Construções dos palácios de Cnossos, Mália e Festo.</label>
                <br>
                <input type="radio" id="one" value="d" v-model="editedItem.question2">
                <label for="four">d) Conquista e colonização do mediterrâneo pelos povos gregos, permitindo o estímulo de uma rede comercial de troca de matéria-prima.</label>
                <br>
                <input type="radio" id="one" value="e" v-model="editedItem.question2">
                <label for="five">e) Época de grande explosão de novas correntes filosóficas e científicas, mas ao mesmo tempo um período marcado por intensas guerras.</label>
                <br>
                <br>
                <br>
                <h3 style="margin: 0">3. Sobre as Guerras Médicas, assinale a alternativa incorreta: "</h3>
                <input type="radio" id="one" value="a" v-model="editedItem.question3">
                <label for="one">a) Leonidas I venceu a batalha de Termópilas.</label>
                <br>
                <input type="radio" id="one" value="b" v-model="editedItem.question3">
                <label for="two">b) O imperador persa Darius I inicia sua invasão de Ática aproximadamente no ano de 490 a.C.</label>
                <br>
                <input type="radio" id="one" value="c" v-model="editedItem.question3">
                <label for="three">c) Após a morte de Darius I, seu filho Xerxes I é quem assume a invasão da Grécia.</label>
                <br>
                <input type="radio" id="one" value="d" v-model="editedItem.question3">
                <label for="four">d) Como estratégia para derrotar a invasão persa, as tribos gregas formam uma união para o fortalecimento de tropas e de suas defesas.</label>
                <br>
                <input type="radio" id="one" value="e" v-model="editedItem.question3">
                <label for="five">e) Leonidas I consegue temporariamente bloquear as tropas persas, mas não evita que o exército de Xerxes invada a Ática.</label>
                <br>
                <br>
                <br>
                <el-form-item class="estilo">
                <el-button class="botao-dialog" type="primary" flat @click="enviar()">Enviar respostas!</el-button>
                <el-button class="botao-dialog" type="danger" flat @click="close()">Cancelar</el-button>
                </el-form-item>   
            </el-form>   
        </el-dialog>
    </el-container>
</template>

<style lang="scss" scoped>
@import "../../styles/variables.scss";

    .container {
        display: flex;
        padding: 5%;
        background: #FFFFFF 0% 0% no-repeat padding-box;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        .texto {
            margin-top: 200px;
            font: Bold 50px Segoe UI;
            color: #10ADB2;
        }

        .button-style {
            width: 400px;
            font: 25px Segoe UI;
            padding-top: 8px !important;
            padding-bottom: 8px !important;
            border-width: 4px !important;
            box-shadow: 0px 3px 6px #00000029;
            color: #10ADB2 !important;
            border-radius: 90px;
            border-color: #10ADB2 !important;
            background-color: rgba(196, 38, 97, 0) !important;
            margin-bottom: 200px;
        }

        .button-style:hover {
            color: #FFFFFF !important;
            background-color: #10ADB2 !important;
        }
    }

    @media screen and (max-width: 500px) {
        .container {
            .texto {
                margin-top: 100px;
                font-size: 30px;
            }

            .button-style {
                width: 200px;
                font-size: 15px;
            }

            .estilo {
                width: 100%;
                 
                .botao-dialog {
                    font-size: 12px;
                    margin: 10px;
                    width: 80%;
                }  
            }         
        }
    }

</style>


<script>
export default {
    data() {
        return {
            dialog: false,

            rules: {
                question1: [
                    {
                        required: '',
                        message: "Por favor, insira um valor válido",
                        trigger: "change"
                    }
                ],
                question2: [
                    {
                        required: '',
                        message: "Por favor, insira um valor válido",
                        trigger: "change"
                    }
                ],
                question3: [
                    {
                        required: '',
                        message: "Por favor, insira um valor válido",
                        trigger: "change"
                    }
                ]
            },

            editedItem: {
                question1: '',
                question2: '',
                question3: ''  
            },

            defaultItem: {
                question1: '',
                question2: '',
                question3: ''                 
            }

        }
    },
    methods: {
        enviar() {
            if(this.editedItem.question1 == '' || this.editedItem.question2 == '' || this.editedItem.question1 == '') {
                confirm("Preencha corretamente os campos!");
            }
            if(this.editedItem.question1 == 'd' && this.editedItem.question2 == 'e' && this.editedItem.question3 == 'a') {
                confirm("Parabéns você acertou: 3/3!");
                this.close();
            }
            if((this.editedItem.question1 == 'd' && this.editedItem.question2 == 'e' && this.editedItem.question3 != 'a')  || (this.editedItem.question2 == 'e' && this.editedItem.question3 == 'a' && this.editedItem.question1 != 'd') ||
               (this.editedItem.question1 == 'd' && this.editedItem.question3 == 'a' && this.editedItem.question2 != 'e')) {
                confirm("Parabéns você acertou: 2/3!");
                this.close();
            }
            if((this.editedItem.question1 == 'd' && this.editedItem.question2 != 'e' && this.editedItem.question3 != 'a')  || (this.editedItem.question2 == 'e' && this.editedItem.question3 != 'a' && this.editedItem.question1 != 'd') ||
               (this.editedItem.question1 != 'd' && this.editedItem.question3 == 'a' && this.editedItem.question2 != 'e')) {
                confirm("Parabéns você acertou: 1/3!");
                this.close();
            }
            if(this.editedItem.question1 != '' && this.editedItem.question1 != 'd' && this.editedItem.question2 != '' && this.editedItem.question2 != 'e' && this.editedItem.question3 != '' && this.editedItem.question3 != 'a') {
                confirm("Que pena, você acertou: 0/0. Volte em nossa videoaula e tente fazer novamente o questionário.");
                this.close();
            }
        },
        close(){
            this.dialog = false;
            setTimeout(() => {
                this.editedItem = Object.assign({}, this.defaultItem);
                this.editedIndex = -1;
            }, 300)
        },

    }
}
</script>