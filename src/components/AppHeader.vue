<script>
export default{
    name: 'AppHeader',
    props: ['message'],
}
</script>

<template>
    <header class="container">
        <h1>{{ message }}</h1>
    </header>
</template>

<style lang="scss" scoped>
</style>