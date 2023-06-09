<template>

    <div>
        <h3>Order</h3>
        <p>ID: {{ id }}</p>
        <p>Telephone Number: {{ telephone_number }}</p>
        <p>Description: {{ description }}</p>
    </div>
    
</template>

<script>
    export default {
        name: 'OrderComponent',

        props: ['id','telephone_number','description']

    }
</script>

<style scoped>

</style>