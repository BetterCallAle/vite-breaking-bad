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
        // add a flag for a loading animation
        this.store.isLoaded = false;
        // export the data api in store.characters
        axios.get("https://www.breakingbadapi.com/api/characters").then((resp) => {
            this.store.characters = resp.data;
            // turn off the loading animation
            this.store.isLoaded = true;
        })
    },
    methods:{
        loadCharacters(){
            console.log("selezione cambiata");
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
