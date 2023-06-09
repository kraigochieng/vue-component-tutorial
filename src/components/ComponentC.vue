<template>
    <div>
        <p>Component C</p>
        <ComponentE />
    </div>
</template>

<script>
import ComponentE from './ComponentE.vue';

    export default {
        name: 'ComponentC',

        components: {
            ComponentE
        }
    }
</script>

<style scoped>

</style>