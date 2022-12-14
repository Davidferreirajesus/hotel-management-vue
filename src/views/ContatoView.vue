<template>
  <main class="contato-responsivo ">
    <section class="contato-estiloForm section-pd p-top">
      <article>
        <h2 class="h2-primario">Entre em contato conosco</h2>

        <form class="h3-primario " action="">
          <fieldset class="fieldLogin fieldsetLogin">
            <legend class="contato-legenda ">
                Preencha todos os dados 
            </legend>

            <ul class="list-style">
              <li class="contato-li">
                <label for="nome">Nome:</label><br />
                <input class="input-basico"
                  type="text"
                  name="nome"
                  id="nome"
                  size="30"
                  autofocus
                />
              </li>
            </ul>

            <ul class="list-style">
              <li class="contato-li">
                <label for="email">E-mail:</label><br />
                <input class="input-basico" 
                type="text" 
                name="email" 
                id="email" 
                size="30" />
              </li>
            </ul>

            <ul class="list-style">
              <li class="contato-li">
                <label for="telefone">Telefone:</label><br />
                <input class="input-basico" 
                type="text" 
                name="telefone" 
                id="telefone" 
                size="30" />
              </li>
            </ul>

            <ul class="list-style">
              <li class="contato-li">
                <label for="assuntos"
                  >Escolha o assunto que deseja falar:</label
                ><br />
                <select name="assuntos_opt" id="assuntos_opt">
                  <option value="null_opc"></option>
                  <option value="cancelamento">
                    Cancelamento de Reserva
                  </option>
                  <option value="financeiro">Departamento Financeiro</option>
                  <option value="ouvidoria">Ouvidoria</option>
                </select>
              </li>
            </ul>

            <ul class="list-style">
              <li class="contato-li">
                <label for="nome">Digite sua mensagem:</label><br />
                <textarea
                  name="textArea form-control"
                  id="textArea"
                  class="contato-textArea "
                  cols="40"
                  rows="10"
                ></textarea>
              </li>
            </ul>

            <ul class="contato-div-button">
              <ButtonSubmit tipo="Enviar" class="contato-button btn-terceario" />
            </ul>
            
          </fieldset>
        </form>
      </article>
    </section>
    <aside class="esconder"></aside>
  </main>
</template>

<script>
import ButtonSubmit from '@/components/ButtonSubmit.vue'

export default {
  name: "ContatoView",
  components: {
    ButtonSubmit
  }
}
</script>