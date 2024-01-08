<script>
export default{
    name: 'SingleCard',
    props: {
        info: Object
    }
}
</script>

<template>
    <div class="card text-center">
        <img src="" alt="descrizione personaggio">
        <h4>{{ data.name }}</h4>
        <h5>Tipo carta</h5>
    </div>
</template>

<style lang="scss" scoped>
.card {
    width: 50%;
}
</style>