<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import AppSelector from "./components/AppSelector.vue";
import AppMain from "./components/AppMain.vue";
import AppLoader from "./components/AppLoader.vue";
import { store } from "./store"

export default{
    components: {
        AppHeader,
        AppSelector,
        AppMain,
        AppLoader
    },

    data() {
        return {
            store
        }
    },
    created() {
       this.loadCharacters()
    },
    methods:{
        loadCharacters(){
             // add a flag for a loading animation
            this.store.isLoaded = false;
            //create a variable with the API URL
            let apiUrl = "https://www.breakingbadapi.com/api/characters"
            //if "Better Call Saul" is selected, show only the Better Call Saul's characters else if "Breaking Bad" is selected, show only the Breaking Bad Characters
            if(this.store.optionValue){
                apiUrl += `?category=${this.store.optionValue}`
            } 
            // export the data api in store.characters
            axios.get(apiUrl)
            .then((resp) => {
                this.store.characters = resp.data;
                // turn off the loading animation
                this.store.isLoaded = true;
        })
        }
    }
  
}

</script>

<template>
    <AppHeader />

    <main>
        <AppSelector @optionChanged="loadCharacters" />
        <!-- Loading -->
        <AppLoader v-if="!store.isLoaded" />
        <!-- Main after the loading screen -->
        <AppMain v-else />
    </main>
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
</style>
