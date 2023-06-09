<template>
    <div class="card">
        <slot>Default Content</slot>
    </div>
</template>

<script>
    export default {
        name: 'CardComponent',

    }
</script>

<style scoped>
    .card {
        border: solid 1px black;
    }
</style>