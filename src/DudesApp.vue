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
<!-- I get and push data into filed characters:[] from child CreateDudeForm.vue -->
    <create-dude-form 
        @new-preview="newDude = $event"
        @add-dude="characters.push($event)" 
    />

    <p class="preview">
        {{ newDude }}
    </p>


</template>

<script>
import Dude from "./components/Dude.vue"
import CreateDudeForm from './components/CreateDudeForm.vue'

    export default {
        components: {
            Dude, CreateDudeForm,
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