<template>
    <div>
        <h3>{{ title }}</h3>
        <p>Number of likes: {{ likes }}</p>
        <p>Is Published: {{ isPublished ? 'Yes' : 'No'}}</p>
    </div>
</template>

<script>
    export default {

        name: 'ArticlePage',

        props: {
            title: {
                type: String,
                required: true,
                default: 'Default Title',
            },
            likes: Number,
            isPublished: Boolean,
        }

    }
</script>

<style scoped>

</style>