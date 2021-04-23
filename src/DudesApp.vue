<template>

    <ul>
        <li v-for="(dude, index) in characters"
            :key="index"
        >
        <!-- name="dude" I send value from "" -->
        <!-- :name="dude" I send values from data() from field: characters -->
            <Dude :name="dude" lol="hello, my good dude" />
        </li>
    </ul>
<!--
    <form @submit.prevent="characters.push(newDude)" 
          action="" 
          class="add-new">
        <input v-model="newDude" type="text" />
    </form>
-->
<!-- @new-preview is only for send data for mirror element <p class:"preview"> -->
<!-- I get and push data into filed characters:[] from child CreateDudeForm.vue -->
    <create-dude-form 
        @new-preview="newDude = $event"
        @add-dude="characters.push($event)" 
    />

    <preview-dude />

</template>

<script>
import Dude from "./components/Dude.vue"
import PreviewDude from './components/PreviewDude.vue'
import CreateDudeForm from './components/CreateDudeForm.vue'


    export default {
        components: {
            Dude, CreateDudeForm, PreviewDude,
        },
        data() {
            return {
                newDude: '',
                characters: [
                    'Jake the Dog',
                    'Finn the Human',
                    'Marceline the Vampire'
                ],
            }
        },    
    }

</script>

<style lang="scss" scoped>

</style>