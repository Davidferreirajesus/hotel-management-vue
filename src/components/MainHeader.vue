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
            <a class="header--logo" href="/pages/home.html" title="Grand Hoyal Hotel"></a>
            <div class="header--container2">
                <ul class="header--container2-container">
                    <li class="header--container2-item">
                        <a href="#" class="header--container2-link text-bege">
                            <i class="fa-brands fa-whatsapp fa-2x"></i>
                        </a>
                    </li>
                    <li class="header--container2-item">
                        <a href="#" class="header--container2-link text-bege">
                            <i class="fa-brands fa-instagram fa-2x"></i>
                        </a>
                    </li>
                    <li class="header--container2-item">
                        <a href="#" class="header--container2-link text-bege">
                            <i class="fa-brands fa-facebook-f fa-2x"></i>
                        </a>
                    </li>
                </ul>
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

export default {
    name: 'MainHeader',
}
</script>

<style scoped>
</style>