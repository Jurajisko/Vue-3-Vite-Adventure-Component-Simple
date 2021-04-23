<template>

        <article>
            {{ name }}
            <span>{{ lol }}</span>
        </article>

</template>

<script>
    export default {
        props: {
            lol: {
                type: String,
                default: 'this is some words about me, I guess',
            },
            name: {
                type: String,
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>