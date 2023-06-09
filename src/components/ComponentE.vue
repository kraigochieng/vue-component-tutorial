<template>
    <div>
        <p>Component E</p>
        <ComponentF/>
    </div>
</template>

<script>
import ComponentF from './ComponentF.vue';
    export default {
        name: 'ComponentE',
        components: {
            ComponentF
        }
    }
</script>

<style scoped>

</style>