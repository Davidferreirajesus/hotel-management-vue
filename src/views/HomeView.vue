<template>
  <main>
    <section class="section-pd">
      <div class="home--banner" id="homeBanner"></div>
      
      <article>
        <div class="p-top">
          <h2 class="h2-primario">Sobre o nosso hotel</h2>
        </div>                                    
        <div class="">
          <p class="p-primario">
              Completamente novo e moderno, o Grand Hoyal Hotel está localizado na região central de XXXXX, próximo a XXXXX. <br/>
              É o destino ideal para descanso, turismo, lua de mel, sessões fotográficas e negócios, com o melhor da hotelaria. <br/>
                Aproveite nossa piscina ao ar livre e desfrute de um delicioso  café da manhã.
          </p>
        </div>
            
        <h3 class="h3-primario">Nossas acomodações</h3>
        <ImagesCarousel tipo="acomodacoes" 
          :imagem1="getImg('acomodacoes/acomodacoes-standard-2.png')"
          :imagem2="getImg('acomodacoes/acomodacoes-luxo-2.png')"
          :imagem3="getImg('acomodacoes/acomodacoes-presidencial-2.png')"
        />
        <div class="p-top">
          <p class="p-primario">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ex maxime dolorum sapiente qui quo velit fugiat iste ratione ullam distinctio, quisquam eaque porro quia asperiores omnis, tempora vero optio harum veniam assumenda quidem vel eveniet earum. Fuga sint esse, expedita, reiciendis quae dolor odio vitae, quod cum incidunt obcaecati dolore?</p>
        </div>

        <div class="p-top">
          <h3 class="h3-primario">Conheça mais sobre nossos serviços</h3>
        </div>
        <p class="p-primario">GASTRONOMIA</p>
        <p class="p-primario">Lorem ipsum dolor sit amet consectetur adipisicing elit. Hic doloremque magnam beatae minima, quas ratione porro qui in voluptatibus ex natus at nesciunt molestias provident, animi repellendus necessitatibus inventore consequatur cum corporis? Id quidem sed quia neque suscipit libero excepturi eligendi. Libero quasi aperiam alias ab numquam a ipsum non.</p>
        <ImagesCarousel tipo="gastronomia"
          :imagem1="getImg('hotel/gastronomia-1.png')"
          :imagem2="getImg('hotel/gastronomia-2.png')"
          :imagem3="getImg('hotel/gastronomia-3.png')"
        />

        <div class="p-top">
          <div class="col">
            <label class="row" for="newsletter">
              <p class="p-primario">Se inscreva na nossa newsletter e receba diariamente notícias e dicas de lugares para se
              hospedar e promoções:</p>
            </label>
            <InputDefault id="newsletter" placeholder="Digite seu email aqui" tipo="email"/>
            <ButtonSubmit tipo="Enviar" class="col btn-terceario" />
          </div>
        </div>

      </article>
    </section>

    <aside class="esconder">
      <p>Espaço reservado para propagandas.</p>
    </aside>
  </main>
</template>

<script>
// @ is an alias to /src
import ImagesCarousel from '@/components/ImagesCarousel.vue'
import InputDefault from '@/components/InputDefault.vue'
import ButtonSubmit from '@/components/ButtonSubmit.vue'

export default {
  name: 'HomeView',
  components: {
    ImagesCarousel,
    InputDefault,
    ButtonSubmit
  },
  methods: {
    getImg(url) {
      return require('../assets/images/' + url)
    }
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

.h3-primario {
  padding: 0 1.5rem;
  text-align: start;
  color: #213242;
  font: "Quicksand";
}
</style>
