<template>
    <div :id="'card'+id" class="acomodacoes--card card">
        <h2 class="acomodacoes--card-titulo"></h2>
        <a href="" class="acomodacoes--card-btn"></a>
    </div>
</template>

<script>
export default {
    name: "AcomodacaoCard",
    props: {
        id: String
    }
}
</script>