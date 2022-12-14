<template>
    <main>
      <div class="p-top" >
        <h3 class="h3-primario">Nossas Acomodações</h3>
        <p class="p-primario" >Descubra as diversas categorias de quartos que o Grand Royal Hotel tem à sua disposição. Projetados para oferecer o máximo conforto, os variados tipos de quartos do nosso hotel foram projetados tendo como base o novo conceito de hotelaria de puro luxo, transformando a sua hospedagem em uma experiência única. Todos eles oferecem amplas áreas e mobiliário moderno e sofisticado.</p>
      </div>

      <div class="p-top" >
        <h3 class="h3-primario">Quartos Presidenciais:</h3>
      </div>
      <div class="acomodacoes acomodacoes--presidencial">
        <AcomodacaoCard id="1"/>
        <AcomodacaoCard id="2"/>
        <AcomodacaoCard id="3"/>
        <div class="p-top">
            <p class="p-primario">Com 80 m², nossas suítes Luxo, dispõem de cama King Size ou Twin e ainda uma confortável área de trabalho. A ampla sala de estar está mobiliada com poltrona, sofá e mesa de café. Os banheiros contam com box separado.</p>          
        </div>
        <details>
          <summary>
            Saiba mais
          </summary>
        </details>
      </div>

      <div class="p-top">
        <h3 class="h3-primario">Quartos Luxo:</h3>
      </div>
      <div class="acomodacoes acomodacoes--luxo">
        <AcomodacaoCard id="4"/>
        <AcomodacaoCard id="5"/>
        <AcomodacaoCard id="6"/>
        <div class="p-top">
            <p class="p-primario">Com 160 m², nossas suítes Presidenciais contam com espaços privilegiados, cozinha, escritório e sala de estar. O dormitório apresenta um espaço grande, único, integrado e muito iluminado, com vista exuberante. Além disso, dispõe de banheiro com uma espaçosa jacuzzi, chuveiro “rain shower” duplo e sauna. Os hóspedes da suíte têm direito a massagens no nosso Spa e podem contar com serviço de concierge e mordomo 24 horas por dia.</p>
        </div>
        <details>
            <summary>
              Saiba mais
            </summary>
          </details>
      </div>

      <div class="p-top">
        <h3 class="h3-primario">Quartos Standard:</h3>
      </div>
      <div class="acomodacoes acomodacoes--standard">
        <AcomodacaoCard id="7"/>
        <AcomodacaoCard id="8"/>
        <AcomodacaoCard id="9"/>
        <div class="p-top">
            <p class="p-primario">Com 80 m², nossas suítes Luxo, dispõem de cama King Size ou Twin e ainda uma confortável área de trabalho. A ampla sala de estar está mobiliada com poltrona, sofá e mesa de café. Os banheiros contam com box separado.</p>          
        </div>
        <details>
            <summary>
              Saiba mais
            </summary>
          </details>
      </div>

      <aside></aside>
    </main>
</template>

<script>
import "@/assets/css/acomodacoes.css"

import AcomodacaoCard from '@/components/AcomodacaoCard.vue'

export default{
  name: 'AcomodacoesView',
  components: {
    AcomodacaoCard
  }
}
</script>