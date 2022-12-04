<template>
    <footer class="container-fluid global-bg-azul m-0 p-1">
        <div class="row">
            <div class="row">
                <div class="col-sm-2 ps-5 d-flex text-sm-center p-2">
                    <img src="@/assets/images/logo/logo--bege.png" class="footer__logo" alt="Logomarca - Grand Royal Hotel" />
                </div>
                <div class="col d-flex align-items-center justify-content-between">
                    <div class="p-1">
                        <MainNavBar />
                    </div>
                </div>
            </div>
            <div class="row">
                <div class="col-sm-6 p-5 color--bege">
                    <div class="row">
                        <i class=" col-sm-2 fa fa-phone fa-1x" aria-hidden="true"></i>
                        <p class=" col-sm-10 color--bege">+55 (11) 9999-9999</p>
                    </div>
                    <div class="row">
                        <i class=" col-sm-2 fa fa-envelope fa-1x" aria-hidden="true"></i>
                        <p class=" col-sm-10 color--bege">contato@granghoyalhotel.com</p>
                    </div>
                    <div class="row">
                        <i class=" col-sm-2 fa fa-map-marker fa-1x" aria-hidden="true"></i>
                        <p class=" col-sm-10 color--bege">Rua Algum Lugar, n° 0 - Centro <br /> São Paulo - Brasil
                        </p>
                    </div>
                    <div class="col">
                        <a><i class="fa-brands fa-whatsapp fa-3x"></i></a>
                        <a><i class="fa-brands fa-instagram fa-3x"></i></a>
                        <a><i class="fa-brands fa-facebook fa-3x"></i></a>
                        <a><i class="fa-brands fa-linkedin-in fa-3x"></i></a>
                    </div>
                </div>
                 <div class="col-sm-6 row color--bege p-5">
                    <a><i class="text-center col-sm-12 fa fa-map fa-5x" aria-hidden="true"></i></a>
                    <p class="text-center color--bege">Veja no maps</p>
                </div>
            </div>
            <div class="row-sm-10 p-1 text-end">
                <span class="color--bege">Grand Hoyal Hotel&copy;2022 - Todos os direitos reservados.</span>
            </div>
        </div>
    </footer>
</template>

<script>
import MainNavBar from '@/components/MainNavBar.vue'

export default {
    name: 'MainFooter',
    components: {
        MainNavBar
    }
}
</script>

<style scoped>

</style>