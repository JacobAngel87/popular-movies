<template>
    <div class="row">
        <!-- Card component creates multiple Show components -->
        <Show v-for="show in shows" v-bind:aShow= "show" v-bind:key= "show.name"></Show>
    </div>
</template>
<script>
// Importing the Show compoenent
import Show from './Show.vue'
export default {
    // Name of compoenent
    name: "Card",
    // shows prop used for passing data from the App.vue
    props:['shows'],
    components: {
        // My components
        Show
    }
}
</script>
<style scoped>

</style>