<template>
    <div>
        <p>Tab C</p>
        <input type="text" v-model="name" placeholder="Name">
    </div>
</template>

<script>
export default {
    name: 'TabCComponent',

    data: function() {
        return {
            name: ''
        }
    }
}
</script>

<style scoped>

</style>