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
        <img :src="info.card_images[0].image_url" alt="descrizione personaggio">
        <h4>{{ info.name }}</h4>
        <h5>{{ info.type }}</h5>
    </div>
</template>

<style lang="scss" scoped>
.card {
    width: 50%;
}
</style>