<template>
    <div>
        <p>Component F</p>
        <p>Username {{ username }}</p>
    </div>
</template>

<script>
    export default {
        name: 'ComponentF',

        inject: ['username'],

    }
</script>

<style scoped>

</style>