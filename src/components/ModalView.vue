<template>
    <div>
        <div class="modal fade" id="modalVue" tabindex="-1" aria-labelledby="modalVueLabel" aria-hidden="true">
            <div class="modal-dialog">
                <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title">Carrinho</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body">
                    
                    <div :v-if="tipo == 'continuar'" id="modalContinuar">
                        <div class="borda-padrao">
                            <h3 class="h3-primario" id="bookingApt_modal"></h3>
                            <img class="imagem-padrao" id="bookingImg_modal" src="" alt="">
                            <div id="modal-quarto">
                                <h4 class="h3-primario">Descrição:</h4>
                                <p class="p-primario"></p>
                                <p class="p-primario"></p>
                            </div>
                        </div>
                        <div class="margin-padrao">Check-in: <span class="" id="bookingCheckIn_modal"></span></div>
                        <div class="margin-padrao">Check-out: <span class="" id="bookingCheckOut_modal"></span></div>
                        <div class="margin-padrao">Pessoas: <span class="" id="bookingQtd_modal"></span></div>
                        <div class="margin-padrao">Serviços Adicionais: <span class="" id="bookingAdd_modal"></span>
                            <details>
                                <summary>Detalhes</summary>
                                <div id="resumoServicosAdicionais"></div>
                            </details>   
                        </div>
                        <hr />
                        <div class="margin-padrao">Valor total: <span class="" id="bookingValor_modal"></span></div>                     
                    </div>

                    <div :v-if="tipo == 'mais_servicos'" id="modalMaisServicos">
                        <div class="borda-padrao">
                            <h3 class="h3-primario" id="bookingApt_modal"></h3>
                            <img class="imagem-padrao" id="bookingImg_modal" src="" alt="">

                            <div id="modal-servicos">
                            </div>
                        </div>
                        <div class="margin-padrao">
                            <ul id="bookingServices_modal"></ul>
                        </div>
                        <hr />
                        <div class="margin-padrao">Valor total: <span class="valorTotal" id="valorTotal">R$ 0</span>
                        </div>
                    </div>

                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Fechar</button>
                </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap/dist/js/bootstrap.js'

export default {
    name: "ModalView",
    props: {
        tipo: String
    }
}
</script>