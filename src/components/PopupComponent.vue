<template>
    <div>
        <p>This is a popup</p>
        <input type="text" v-model="name" placeholder="name"/>
        <button @click="$emit('closePopup', name)">Close Popup</button>
    </div>
</template>

<script>
    export default {
        name: 'PopupComponent',

        emits: {
            closePopup: (name) => {
                if(!name) {
                    return true
                } else {
                    return false
                }
            }
        },

        data() {
            return {

                name: '',

            }
        }
    }
</script>

<style scoped>

</style>