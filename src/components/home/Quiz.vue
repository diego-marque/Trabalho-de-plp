<template>
    <el-container id="quizSection" class="container">
        <el-row class="title">
            <h2 class="texto">Acesse o questionário assim que finalizar a videoaula.</h2>
        </el-row>
        <el-row>
            <el-button class="button-style" flat @click="dialog = true">JÁ ASSISTI AO VÍDEO</el-button>
        </el-row>
        <el-dialog title="Questionário" :visible.sync="dialog" @closed="close()">
            <el-form :model="editedItem" :rules="rules" class="form demo-ruleForm">
                <h3 style="margin: 0">{{ questaoNumero1.questao }}</h3>
                <input type="radio" id="one" value="a" v-model="editedItem.question1">
                <label for="one">{{ questaoNumero1.alternativa_a }}</label>
                <br>
                <input type="radio" id="one" value="b" v-model="editedItem.question1">
                <label for="two">{{ questaoNumero1.alternativa_b }}</label>
                <br>
                <input type="radio" id="one" value="c" v-model="editedItem.question1">
                <label for="three">{{ questaoNumero1.alternativa_c }}</label>
                <br>
                <input type="radio" id="one" value="d" v-model="editedItem.question1">
                <label for="four">{{ questaoNumero1.alternativa_d }}</label>
                <br>
                <input type="radio" id="one" value="e" v-model="editedItem.question1">
                <label for="five">{{ questaoNumero1.alternativa_e }}</label>
                <br>
                <br>
                <br>
                <h3 style="margin: 0">{{ questaoNumero2.questao }}</h3>
                <input type="radio" id="one" value="a" v-model="editedItem.question2">
                <label for="one">{{ questaoNumero2.alternativa_a }}</label>
                <br>
                <input type="radio" id="one" value="b" v-model="editedItem.question2">
                <label for="two">{{ questaoNumero2.alternativa_b }}</label>
                <br>
                <input type="radio" id="one" value="c" v-model="editedItem.question2">
                <label for="three">{{ questaoNumero2.alternativa_c }}</label>
                <br>
                <input type="radio" id="one" value="d" v-model="editedItem.question2">
                <label for="four">{{ questaoNumero2.alternativa_d }}</label>
                <br>
                <input type="radio" id="one" value="e" v-model="editedItem.question2">
                <label for="five">{{ questaoNumero2.alternativa_e }}</label>
                <br>
                <br>
                <br>
                <h3 style="margin: 0">{{ questaoNumero3.questao }}</h3>
                <input type="radio" id="one" value="a" v-model="editedItem.question3">
                <label for="one">{{ questaoNumero3.alternativa_a }}</label>
                <br>
                <input type="radio" id="one" value="b" v-model="editedItem.question3">
                <label for="two">{{ questaoNumero3.alternativa_b }}</label>
                <br>
                <input type="radio" id="one" value="c" v-model="editedItem.question3">
                <label for="three">{{ questaoNumero3.alternativa_c }}</label>
                <br>
                <input type="radio" id="one" value="d" v-model="editedItem.question3">
                <label for="four">{{ questaoNumero3.alternativa_d }}</label>
                <br>
                <input type="radio" id="one" value="e" v-model="editedItem.question3">
                <label for="five">{{ questaoNumero3.alternativa_e }}</label>
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

        .title {
            display: flex;
            text-align: center;
        }

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
                    font-size: 9px;
                    margin: 10px;
                    width: 84%;
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

            questaoNumero1: {
                questao: '1. Qual dessas cidades da antiguidade eram consideradas polis gregas?',
                alternativa_a: 'a) Ur.',
                alternativa_b: 'b) Roma.',
                alternativa_c: 'c) Cartago.',
                alternativa_d: 'd) Esparta.',
                alternativa_e: 'e) Vaticano.',
            },

            questaoNumero2: {
                questao: '2. De acordo com a vídeo-aula apresentada acima, assinale a alternativa que corresponde a manifestações que ocorreram no período clássico:',
                alternativa_a: 'a) Surgimento dos jogos olímpicos como uma forma de manifestação religiosa e experiência atlética, além da competição entre as cidades-estado da região.',
                alternativa_b: 'b) Aparecimento da civilização Minoica, durante a Idade do Bronze grega, na região de Creta.',
                alternativa_c: 'c) Construções dos palácios de Cnossos, Mália e Festo.',
                alternativa_d: 'd) Conquista e colonização do mediterrâneo pelos povos gregos, permitindo o estímulo de uma rede comercial de troca de matéria-prima.',
                alternativa_e: 'e) Época de grande explosão de novas correntes filosóficas e científicas, mas ao mesmo tempo um período marcado por intensas guerras.',
            },

            questaoNumero3: {
                questao: '3. Sobre as Guerras Médicas, assinale a alternativa incorreta:',
                alternativa_a: 'a) Leonidas I venceu a batalha de Termópilas.',
                alternativa_b: 'b) O imperador persa Darius I inicia sua invasão de Ática aproximadamente no ano de 490 a.C.',
                alternativa_c: 'c) Após a morte de Darius I, seu filho Xerxes I é quem assume a invasão da Grécia.',
                alternativa_d: 'd) Como estratégia para derrotar a invasão persa, as tribos gregas formam uma união para o fortalecimento de tropas e de suas defesas.',
                alternativa_e: 'e) Leonidas I consegue temporariamente bloquear as tropas persas, mas não evita que o exército de Xerxes invada a Ática.',
            },

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
            if(this.editedItem.question1 == '' || this.editedItem.question2 == '' || this.editedItem.question3 == '') {
                confirm("Preencha corretamente os campos!");
            }
            else if(this.editedItem.question1 == 'd' && this.editedItem.question2 == 'e' && this.editedItem.question3 == 'a') {
                confirm("Parabéns você acertou: 3/3!");
                this.close();
            }
            else if((this.editedItem.question1 == 'd' && this.editedItem.question2 == 'e' && this.editedItem.question3 != 'a')  || (this.editedItem.question2 == 'e' && this.editedItem.question3 == 'a' && this.editedItem.question1 != 'd') ||
               (this.editedItem.question1 == 'd' && this.editedItem.question3 == 'a' && this.editedItem.question2 != 'e')) {
                confirm("Quase chegou lá, você acertou: 2/3!");
                this.close();
            }
            else if((this.editedItem.question1 == 'd' && this.editedItem.question2 != 'e' && this.editedItem.question3 != 'a')  || (this.editedItem.question2 == 'e' && this.editedItem.question3 != 'a' && this.editedItem.question1 != 'd') ||
               (this.editedItem.question1 != 'd' && this.editedItem.question3 == 'a' && this.editedItem.question2 != 'e')) {
                confirm("Você acertou: 1/3!");
                this.close();
            }
            else if(this.editedItem.question1 != '' && this.editedItem.question1 != 'd' && this.editedItem.question2 != '' && this.editedItem.question2 != 'e' && this.editedItem.question3 != '' && this.editedItem.question3 != 'a') {
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