<template>
    <div>
        <p v-for="(name, index) in names" :key="index">
            <slot name="first_name" :first_name="name.first_name">

            </slot>
            <slot name='last_name' :last_name="name.last_name">

            </slot>
            <!-- {{ name.first_name }} {{ name.last_name }} -->
        </p>
    </div>
</template>

<script>
export default {
    name: 'NamesComponent',

    data: function() {
        return {
            names: [
                {
                    first_name: 'Kraig',
                    last_name: 'Ochieng',
                },
                {
                    first_name: 'James',
                    last_name: 'Muiruri',
                },
                {
                    first_name: 'Lisa',
                    last_name: 'Nyaboke',
                }
            ],
        }
        
    }
}
</script>

<style scoped>

</style>