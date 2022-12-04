<template>
    <header class="header--container container-fluid text-end m-0 p-1">
        <div class="container" id="logado">
            <span class="col p-1" id="logado-usuario"></span>
            <button class="btn btn-secondary text-bg-secondary col p-1 ">
                Sair
            </button>
        </div>
        <!-- <div class="container" id="cadastro">
            <button class="btn btn-secondary col p-1">
                Cadastre-se
            </button>
        </div> -->
        <div class="d-flex align-items-center">
            <router-link to="/" class="header--logo" title="Grand Hoyal Hotel"></router-link>
            <div class="header--container2">
                <SocialMedia />
                <p class="header--container2-container alinhamento m-1 p-1">
                    A sofisticação e o conforto ideal.<br />
                    Vem ser Grand, vem ser Royal!
                </p>
            </div>
        </div>
    </header>
</template>

<script>
import "@/assets/css/main.css"
import "@/assets/css/header-footer.css"

import SocialMedia from '@/components/SocialMedia.vue'

export default {
    name: 'MainHeader',
    components: {
        SocialMedia
    }
}
</script>

<style scoped>
</style>