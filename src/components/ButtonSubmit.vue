<template>
    <input type="submit" :value="tipo" class="col">
</template>

<script>
export default {
    name: "ButtonSubmit",
    props: {
        tipo: String,
    }
}
</script>