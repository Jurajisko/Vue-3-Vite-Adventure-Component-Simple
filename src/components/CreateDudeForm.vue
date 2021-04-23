<template>

    <form @submit.prevent="formSubmitted" class="add-new">
        <input @input="valueChanged" 
                v-model="newName" 
                type="text" />
    </form>

</template>

<script>
    export default {
        data() {
            return {
                newName: '',
            }
        },
        methods: {
            formSubmitted() {
                if (!this.newName) return;
                // $emit is ready only from child to parent
                this.$emit( 'add-dude', this.newName )
                this.newName = ''
                // send set into PreviewDude.vue for empty field after enter
                window.eventBus.emit( 'new-preview', '' )

            },
            valueChanged(e) {
                if (!this.newName) return;
                // eventBus (check main.js) is ready global in our app with window.
                // and work with data from PreviewDude.vue
                window.eventBus.emit( 'new-preview', this.newName )
            },
        },
    }
</script>

<style lang="scss" scoped>

</style>