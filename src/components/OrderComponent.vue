<template>

    <div>
        <h3>Order</h3>
        <p>ID: {{ id }}</p>
        <p>Telephone Number: {{ telephone_number }}</p>
        <p v-if="description===''">Description: none</p>
        <p v-else>Description: {{ description }}</p>
    </div>
    
</template>

<script>
    export default {
        name: 'OrderComponent',

        props: {
            id: {
                type: String,
                required: true
            },
            telephone_number: String,
            description: {
                type: String,
                default: 'none',
            }
        },

    }
</script>

<style scoped>

</style>