<template>
    <label class="row" :for="id">
        <p class="p-primario">Se inscreva na nossa newsletter e receba diariamente notícias e dicas de lugares para se
        hospedar e promoções:</p>
    </label>
    <input class="input-padrao p-primario" type="text" :id="id" :placeholder="placeholder">
</template>

<script>
export default {
    name: "InputText",
    props: {
        id: String,
        placeholder: String,
    }
}
</script>