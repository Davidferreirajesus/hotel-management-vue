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

    <ModalView tipo='continuar' />
    <ModalView tipo='mais_servicos' />
    
</template>

<script>
import ModalView from '@/components/ModalView.vue'

export default {
    name:'ReservasView',
    data(){
        return{
            checkin: localStorage.getItem('checkin'),
            checkout: localStorage.getItem('checkout'),
            qtdPessoas: localStorage.getItem('qtdPessoas')
            
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
        },
        choiceApt(name){
            document.querySelector('#bookingApt').innerText = name
        },
        showModal(id) {
            if (id == 'mais_servicos') {
                document.querySelector('#modalContinuar').classList.add('esconder')
                document.querySelector('#modalMaisServicos').classList.remove('esconder')
                console.log('SERV')
            }
            else if (id == 'continuar') {
                document.querySelector('#modalMaisServicos').classList.add('esconder')
                document.querySelector('#modalContinuar').classList.remove('esconder')
                console.log('CONT')

            }
        }
    }
}
</script>
