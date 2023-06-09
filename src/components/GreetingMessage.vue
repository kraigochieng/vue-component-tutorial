<template>
    <p>Hello {{ name }}</p>
</template>

<script>

export default {

    name: "GreetingMessage",

    props: ['name']
}

</script>

<style scoped>
</style>