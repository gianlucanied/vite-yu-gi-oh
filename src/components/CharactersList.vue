<script>
import SingleCard from './SingleCard.Vue'
export default{
    name: 'CharactersList',
    components: {
        SingleCard
    }
}
</script>

<template>
    <section class="container">
        <div class="col-4">
            <SingleCard/>
        </div>
    </section>
</template>

<style lang="scss" scoped>
</style>