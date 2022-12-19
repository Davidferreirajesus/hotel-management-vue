<template>
    <main>
        <section>

            <fieldset>
                <div class="myReservation p-top">
                    <h2 class="h2-primario ">Minha Reserva</h2>
                    <p class="p-primario">
                        Forneça a data de entrada, saída e quantidade de pessoas.
                    </p>
                    <span class="margin-left">
                        <input v-model="checkin" v-on:change="onChangeCheckin" class="input-padrao" type="date" name="checkin" id="checkin" required>
                        <input v-model="checkout" v-on:change="onChangeCheckout" class="input-padrao" type="date" name="checkout" id="checkout" required>
                        <input v-model="qtdPessoas" v-on:change="onChangeQtdPessoas" class="input-padrao" type="number" name="qtdPessoas" id="qtdPessoas" min="1" max="4" required>
                    </span>
                    <p class="p-primario">Escolha o quarto</p>
                </div>
                <section class="display-grid">
                    <article class=" ">
                        <div class="display-grid borda-padrao">
                            <img class="imagem-padrao" src="@/assets/images/acomodacoes/acomodacoes-presidencial-1.png" alt="">
                            <div class=" ">
                                <h3 class="h3-primario">Executive</h3>
                                <p class="p-primario">Executive ipsum dolor sit amet consectetur adipisicing elit. Sit
                                    nobis aliquam quibusdam aliquid quam perferendis autem eum numquam earum nam
                                    corporis mollitia cumque error, id quod laboriosam presidencial.</p>
                                <p class="p-primario">R$190,00</p>
                                <div class="p-primario">
                                    <label for="executive"> <input v-on:click="choiceApt('Executive')" class="radioRoomChoice" type="radio"
                                            name="roomChoice" id="executive" value="executive" required><span>
                                            Selecionar o quarto Presidencial</span></label>
                                </div>

                            </div>
                        </div>
                        <div class="display-grid borda-padrao">
                            <img class="imagem-padrao" src="@/assets/images/acomodacoes/acomodacoes-luxo-1.png" alt="">
                            <div>
                                <h3 class="h3-primario">Classic</h3>
                                <p class="p-primario">Luxo ipsum dolor sit amet consectetur adipisicing elit. Sit nobis
                                    aliquam quibusdam aliquid quam perferendis autem eum numquam earum nam corporis
                                    mollitia cumque error, id quod laboriosam luxo.</p>
                                <p class="p-primario">
                                    R$250,00
                                </p>

                                <div class="p-primario">
                                    <label for="classic"> <input v-on:click="choiceApt('Classic')" class="radioRoomChoice" type="radio" name="roomChoice"
                                            id="classic" value="classic" required><span> Selecionar o quarto
                                            Luxo</span></label>
                                </div>

                            </div>
                        </div>
                        <div class="display-grid borda-padrao">
                            <img class="imagem-padrao" src="@/assets/images/acomodacoes/acomodacoes-standard-1.png" alt="">
                            <div>
                                <h3 class="h3-primario">Premium</h3>
                                <p class="p-primario">Standard ipsum dolor sit amet consectetur adipisicing elit. Sit
                                    nobis aliquam quibusdam aliquid quam perferendis autem eum numquam earum nam
                                    corporis mollitia cumque error, id quod laboriosam standard.
                                </p>
                                <p class="p-primario">
                                    R$400,00
                                </p>
                                <div class="p-primario">
                                    <label for="premium"> <input v-on:click="choiceApt('Premium')" class="radioRoomChoice" type="radio" name="roomChoice"
                                            id="premium" value="premium" required><span> Selecionar o quarto
                                            Standard</span></label>
                                </div>
                            </div>
                        </div>
                    </article>
                    <div class=" borda-resumo-reserva resumo-reserva">
                        <article class="resumo-reserva-conteudo" id="bookingSummary">
                            <h3 class="h3-resumo-reservas">Resumo da reserva</h3>
                            <div class="box-reservas">
                                <div class="margin-padrao">Apartamento: <span class="" id="bookingApt"></span></div>
                                <div class="margin-padrao">Check-in: <span class="" id="bookingCheckIn"></span></div>
                                <div class="margin-padrao">Check-out: <span class="" id="bookingCheckOut"></span></div>
                                <div class="margin-padrao">Pessoas: <span class="" id="bookingQtd"></span></div>
                                <div class="margin-padrao esconder">Valor total: <span class=""
                                        id="bookingValor"></span></div>
                            </div>
                            <div>
                                <p><a class="link-padrao h3-primario" id="maisServicos" data-bs-toggle="modal" data-bs-target="#modalVue"
                                    @click="showModal('mais_servicos')"><i
                                            class="fa fa-plus fa-2x" aria-hidden="true"></i> MAIS SERVIÇOS</a></p>

                            </div>
                            <div class="centralizar">
                                <button class="btn-texto btn-resumo-reservas text-light" data-bs-toggle="modal" data-bs-target="#modalVue"
                                    @click="showModal('continuar')" id="continuar">CONTINUAR</button>
                            </div>
                        </article>
                    </div>
                </section>
            </fieldset>

        </section>
        
        <aside class="esconder">
            <p>Espaço reservado para propagandas.</p>
        </aside>
    </main>

    <ModalView  />
    
</template>

<script>
import ModalView from '@/components/ModalView.vue'

export default {
    name:'ReservasView',
    data(){
        return{
            checkin: localStorage.getItem('checkin'),
            checkout: localStorage.getItem('checkout'),
            qtdPessoas: localStorage.getItem('qtdPessoas'),
            quartos: [
                {
                    nome: "executive",
                    valor: 190,
                    descricao:
                    "Descrição EXECUTIVE Standard ipsum dolor sit amet consectetur adipisicing elit. Sit nobis aliquam quibusdam aliquid quam perferendis autem eum numquam earum nam corporis mollitia cumque error, id quod laboriosam standard.",
                },
                {
                    nome: "classic",
                    valor: 250,
                    descricao:
                    "Descrição CLASSIC Standard ipsum dolor sit amet consectetur adipisicing elit. Sit nobis aliquam quibusdam aliquid quam perferendis autem eum numquam earum nam corporis mollitia cumque error, id quod laboriosam standard.",
                },
                {
                    nome: "premium",
                    valor: 400,
                    descricao:
                    "Descrição PREMIUM Standard ipsum dolor sit amet consectetur adipisicing elit. Sit nobis aliquam quibusdam aliquid quam perferendis autem eum numquam earum nam corporis mollitia cumque error, id quod laboriosam standard.",
                },
            ],
            servicosAdicionais: [
                {
                    nome: "Academia",
                    preco: 100,
                },
                {
                    nome: "Early check-in/Late Check-in",
                    preco: 50,
                },
                {
                    nome: "Café da manhã",
                    preco: 190,
                },
                {
                    nome: "Serviço de lavanderia",
                    preco: 100,
                },
                {
                    nome: "Serviço de spa",
                    preco: 250,
                },
            ],
            criaInputNumber: '',
            criaSpan: '',
            precoServico: '',
            inpServicosQtd: '',
            inputServicos: '',
            arrayValorServicos: [], 
            valorTServicos: ''
        }
    },
    components: {
        ModalView
    },
    methods:{
        onChangeCheckin(){
            const checkin = document.querySelector('#checkin');
            const checkout = document.querySelector('#checkout');
            localStorage.setItem('checkin', checkin.value);
            document.querySelector('#bookingCheckIn').innerText = localStorage.getItem('checkin')
            checkout.value = ''
            document.querySelector('#bookingCheckOut').innerText = ''
            localStorage.removeItem('checkout')

        },
        onChangeCheckout() {
            const checkout = document.querySelector('#checkout');
            const checkin = document.querySelector('#checkin');
            if (checkout.value > checkin.value) {
                localStorage.setItem('checkout', checkout.value);
                document.querySelector('#bookingCheckOut').innerText = localStorage.getItem('checkout')
            }else{
                alert('A data do check-out deve ser posterior a de check-in')
                checkout.value = ''
            }
        },
        onChangeQtdPessoas() {
            const qtdPessoas = document.querySelector('#qtdPessoas');
            localStorage.setItem('qtdPessoas', qtdPessoas.value);
            document.querySelector('#bookingQtd').innerText = localStorage.getItem('qtdPessoas')
            const that = this

            //zera servicos caso a qtdPessoas seja inferior a quantidade de determinado serviço e atualiza o preço total de serviços
            this.inpServicosQtd.forEach(function(valorInput, index){
                if(valorInput.value > qtdPessoas.value){
                valorInput.value = 0
                localStorage.setItem(`inpServicosQtd${index+1}`, valorInput.value)
                that.arrayValorServicos[index] = that.servicosAdicionais[index].preco * valorInput.value
                that.valorTServicos = that.arrayValorServicos.reduce((somaParcial, a) => somaParcial + a, 0);
                document.querySelector("#valorTotal").innerHTML = `R$${that.valorTServicos.toFixed(2)}`
                localStorage.setItem("valorTServicos", that.valorTServicos)
                } 
            })
            
            switch (document.querySelector("#bookingApt").innerText) {
                case "Classic":
                document.querySelector("#bookingValor_modal").innerText = `R$ ${(
                    (this.quartos[1]["valor"] * this.qtdAtual) + parseInt(localStorage.getItem("valorTServicos"))
                ).toFixed(2)}`;
                break;
                case "Premium":
                document.querySelector("#bookingValor_modal").innerText = `R$ ${(
                    (this.quartos[2]["valor"] * this.qtdAtual + parseInt(localStorage.getItem("valorTServicos")))
                ).toFixed(2)}`;
                break;
                default:
                document.querySelector("#bookingValor_modal").innerText = `R$ ${(
                    (this.quartos[0]["valor"] * this.qtdAtual) + parseInt(localStorage.getItem("valorTServicos"))
                ).toFixed(2)}`;
                break;
            }
        },
        choiceApt(name){
            document.querySelector('#bookingApt').innerText = name
            localStorage.setItem('quarto', name)
        },
        showModal(id) {
            if (id == 'mais_servicos') {
                document.querySelector('#modalContinuar').classList.add('esconder')
                document.querySelector('#modalMaisServicos').classList.remove('esconder')
                const that = this

                this.inpServicosQtd.forEach(function(valorInput, index){
                    document.querySelector(`#inputServicos:nth-of-type(${index+1})`).setAttribute("max", localStorage.getItem('qtdPessoas'))
                    that.precoServico[index].innerHTML = `${that.servicosAdicionais[index].nome} - R$${(that.servicosAdicionais[index].preco).toFixed(2)}`
                    valorInput.addEventListener("change", function(){
                        localStorage.setItem(`inpServicosQtd${index+1}`, valorInput.value)
                        that.arrayValorServicos[index] = that.servicosAdicionais[index].preco * valorInput.value
                        that.valorTServicos = that.arrayValorServicos.reduce((somaParcial, valorAtual) => somaParcial + valorAtual, 0);
                        document.querySelector("#valorTotal").innerHTML = `R$${that.valorTServicos.toFixed(2)}`
                        console.log(`R$${that.valorTServicos.toFixed(2)}`)
                        localStorage.setItem("valorTServicos", that.valorTServicos)
                    })
                    that.arrayValorServicos[index] = that.servicosAdicionais[index].preco * valorInput.value
                })
            }
            else if (id == 'continuar') {
                document.querySelector('#modalMaisServicos').classList.add('esconder')
                document.querySelector('#modalContinuar').classList.remove('esconder')

                if (
                    localStorage.getItem("quarto") &&
                    localStorage.getItem("checkin") &&
                    localStorage.getItem("checkout") &&
                    localStorage.getItem("qtdPessoas")
                ) {
                    document.querySelector("#bookingApt_modal").innerText =
                    localStorage.getItem("quarto")[0].toUpperCase() +
                    localStorage.getItem("quarto").substr(1);
                    document.querySelector("#bookingCheckIn_modal").innerText =
                    localStorage.getItem("checkin");
                    document.querySelector("#bookingCheckOut_modal").innerText =
                    localStorage.getItem("checkout");
                    document.querySelector("#bookingQtd_modal").innerText =
                    localStorage.getItem("qtdPessoas");
                    document.querySelector("#bookingAdd_modal").innerText = 
                        `R$ ${parseInt(localStorage.getItem("valorTServicos")).toFixed(2)}`;

                    switch (localStorage.getItem("quarto")) {
                        case "Classic":
                            document.querySelector("#modal-quarto p:nth-of-type(1)").innerText =
                            this.quartos[1]["descricao"];
                            document.querySelector(
                            "#modal-quarto p:nth-of-type(2)"
                            ).innerText = `R$ ${this.quartos[1]["valor"].toFixed(2)}`;
                            document.querySelector("#bookingImg_modal").src = require(
                            "@/assets/images/acomodacoes/acomodacoes-luxo-1.png");
                            document.querySelector("#bookingValor_modal").innerText = `R$ ${(
                            (this.quartos[1]["valor"] * this.qtdPessoas) + parseInt(localStorage.getItem("valorTServicos"))
                            ).toFixed(2)}`;
                            break;
                        case "Premium":
                            document.querySelector("#modal-quarto p:nth-of-type(1)").innerText =
                            this.quartos[2]["descricao"];
                            document.querySelector(
                            "#modal-quarto p:nth-of-type(2)"
                            ).innerText = `R$ ${this.quartos[2]["valor"].toFixed(2)}`;
                            document.querySelector("#bookingImg_modal").src = require(
                            "@/assets/images/acomodacoes/acomodacoes-standard-1.png");
                            document.querySelector("#bookingValor_modal").innerText = `R$ ${(
                            (this.quartos[2]["valor"] * this.qtdPessoas) + parseInt(localStorage.getItem("valorTServicos"))
                            ).toFixed(2)}`;
                            break;
                        default:
                            document.querySelector("#modal-quarto p:nth-of-type(1)").innerText =
                            this.quartos[0]["descricao"];
                            document.querySelector(
                            "#modal-quarto p:nth-of-type(2)"
                            ).innerText = `R$ ${this.quartos[0]["valor"].toFixed(2)}`;
                            document.querySelector("#bookingImg_modal").src = require(
                            "@/assets/images/acomodacoes/acomodacoes-presidencial-1.png");
                            document.querySelector("#bookingValor_modal").innerText = `R$ ${(
                            (this.quartos[0]["valor"] * this.qtdPessoas) + parseInt(localStorage.getItem("valorTServicos"))
                            ).toFixed(2)}`;
                            break;
                        }

                }

                //Deleta todos os spans da div #resumoServicosAdicionais enquanto tiver filhos, para evitar duplicação/acumulação de texto
                const divServicosAdicionais = document.getElementById("resumoServicosAdicionais");
                    while (divServicosAdicionais.firstChild) {
                    divServicosAdicionais.removeChild(divServicosAdicionais.lastChild);
                }

                //cria os spans com os textos incluindo os serviços adicionais escolhidos no modal de mais serviços
                const that = this 
                this.inpServicosQtd.forEach(function(valorInput, index){
                    if(valorInput.value != 0){
                        that.criaSpan = document.createElement("span")
                        that.criaSpan.setAttribute("class", "detalhesServicosAdicionais")
                        that.criaSpan.setAttribute("class", "d-block")
                        document.getElementById("resumoServicosAdicionais").appendChild(that.criaSpan)
                        that.criaSpan.innerHTML = `${that.servicosAdicionais[index].nome} x${valorInput.value}`
                    }
                })

                //verifica se a div #resumoServicosAdicionais não possui filhos, se verdadeiro cria um texto pro usuário considerar escolher um
                if(document.getElementById('resumoServicosAdicionais').childElementCount == 0){
                    this.criaSpan = document.createElement("span")
                    this.criaSpan.setAttribute("class", "semServico")
                    document.getElementById("resumoServicosAdicionais").appendChild(this.criaSpan)
                    this.criaSpan.innerHTML = `Nenhum serviço escolhido, favor considere`
                }
            } else {
                alert("Por favor, preencha todos os campos!");
            }
        }
    },
    mounted: function() {
        // Carrega informações do localstorage (caso já exista)
        if (localStorage.getItem("checkin")) {
            document.querySelector("#bookingCheckIn").innerText =
                localStorage.getItem("checkin");
        }

        if (localStorage.getItem("checkout")) {
            document.querySelector("#bookingCheckOut").innerText =
                localStorage.getItem("checkout");
        }

        if (localStorage.getItem("qtdPessoas")) {
            document.querySelector("#bookingQtd").innerText = localStorage.getItem("qtdPessoas");
        }

        if (localStorage.getItem("quarto")) {
            switch (localStorage.getItem("quarto")) {
                case "Classic":
                    document.querySelector("#bookingApt").innerText = "Classic";
                    document.querySelector("#bookingValor_modal").innerText = `R$ ${(
                        (this.quartos[1]["valor"] * this.qtdPessoas) + parseInt(localStorage.getItem("valorTServicos"))
                    ).toFixed(2)}`;
                    document.querySelector("#classic").checked = true;
                    break;
                case "Premium":
                    document.querySelector("#bookingApt").innerText = "Premium";
                    document.querySelector("#bookingValor_modal").innerText = `R$ ${(
                        (this.quartos[2]["valor"] * this.qtdPessoas) + parseInt(localStorage.getItem("valorTServicos"))
                    ).toFixed(2)}`;
                    document.querySelector("#premium").checked = true;
                    break;
                default:
                    document.querySelector("#bookingApt").innerText = "Executive";
                    document.querySelector("#bookingValor_modal").innerText = `R$ ${(
                        (this.quartos[0]["valor"] * this.qtdPessoas) + parseInt(localStorage.getItem("valorTServicos"))
                    ).toFixed(2)}`;
                    document.querySelector("#executive").checked = true;
                    break;
            }
        }
        
        for(let i = 1; i <= this.servicosAdicionais.length; i++){
            this.criaInputNumber = document.createElement("input")
            this.criaSpan = document.createElement("span")
            this.criaInputNumber.setAttribute("type", "number")
            this.criaInputNumber.setAttribute("min", "0")
            this.criaInputNumber.setAttribute("value", "1")
            this.criaInputNumber.setAttribute("class", "d-block")
            this.criaInputNumber.setAttribute("id", "inputServicos")
            this.criaInputNumber.setAttribute("name", "valores")
            this.criaSpan.setAttribute("class", "precoServico")
            document.getElementById("modal-servicos").appendChild(this.criaSpan);
            document.getElementById("modal-servicos").appendChild(this.criaInputNumber);
            if(i == this.servicosAdicionais.length){
                this.precoServico = document.querySelectorAll(".precoServico")
                this.inpServicosQtd = document.getElementsByName('valores')
                this.inputServicos = document.querySelectorAll("#inputServicos")
            } 
        }

        window.onload = this.inpServicosQtd.forEach(function(valorInput, index){
            localStorage.getItem(`inpServicosQtd${index+1}`) ? valorInput.value = localStorage.getItem(`inpServicosQtd${index+1}`) : null
            localStorage.getItem("valorTServicos") ? document.querySelector("#valorTotal").innerHTML = `R$${parseInt(localStorage.getItem("valorTServicos")).toFixed(2)}` : null
        })

    }
}
</script>

<style scoped>
.esconder {
    display: none;
}
.p-top {
    padding: 1rem 0 0 0;
}

.h2-primario {
    padding: 0 1.5rem;
    text-align: start;
    color: #213242;
    font: "Quicksand";
}

.p-primario {
    padding: 0 1.5rem;
    text-align: start;
    color: #213242;
    font: "Quicksand";
}

.margin-left {
    margin: 0 0.5rem;
}

.display-grid {
    display: grid;
    grid-template-columns: 2fr 1fr;
}

.borda-padrao {
    margin: 3rem;
    padding: 1rem;
    border-radius: 15px;
    box-shadow: 1px 3px 5px #213242;
}

.imagem-padrao {
    margin: 1.5rem;
    width: 90%;
}

.borda-resumo-reserva {
    margin: 10vh 5vh;
    padding: 1rem;
    border-radius: 15px;
    box-shadow: 1px 3px 5px #213242;
}

.borda-resumo-reserva:hover {
    box-shadow: 1px 4px 10px #213242;
}

.resumo-reserva-conteudo {
    margin-top: 3vw;
}

.resumo-reserva {
    height: 35rem;
    position: -webkit-sticky;
    position: sticky;
    top: 0;
}

.h3-resumo-reservas {
    padding: 0 1.5rem;
    text-align: start;
    color: #213242;
    font: "Quicksand";
    text-align: center;
}

.box-reservas {
    background-color: rgba(225, 200, 136, 0.7);
    width: 100%;
    padding: 3%;
    text-align: start;
    margin-top: 2rem;
}

.margin-padrao {
    padding: 0.5rem;
}

.link-padrao {
    padding: 0 1.5rem;
    text-align: start;
    color: #213242;
    font: "Quicksand";
    text-decoration: none;
}

.link-padrao:hover {
    color: #cf9903;
}

.centralizar {
    text-align: center;
    align-items: center;
}

.btn-texto {
    color: white;
    font: "Quicksand";
    text-align: center;
    font-size: 1vw;
}

.btn-resumo-reservas {
    background-color: #213242;
    border: none;
    box-shadow: 3px 1px 8px white inset;
    border-radius: 20px;
    width: 100%;
    height: 3rem;
}

@media (max-width: 1170px) {
    .display-grid {
        display: inline-block;
    }

    .resumo-reserva {
        display: inline-block;
        width: 80%;
        height: 35rem;
    }

    .btn-padrao {
        width: 80%;
    }

    .btn-beje {
        width: 20vh;
        height: 6vh;
        border: 1px solid #e1c888;
        border-radius: 30px;
        background-color: #e1c888;
        box-shadow: 3px 3px 5px #b3b3b4;
    }

    .btn-texto {
        font-size: larger;
    }
}
</style>