<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import AppSelector from "./components/AppSelector.vue";
import AppMain from "./components/AppMain.vue";
import { store } from "./store"

export default{
    components: {
        AppHeader,
        AppSelector,
        AppMain
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
    }
  
}

</script>

<template>
    <AppHeader />

    <main>
        <AppSelector />
        <!-- Loading -->
        <div class="loading text-center" v-if="!store.isLoaded">
            <img src="../src/assets/img/loading.png" alt="Walter White Loading Meme" class="loading-img">
            <span class="loading-txt text-light d-block">Loading...</span>
        </div>
        <!-- Main after the loading screen -->
        <AppMain v-else />
    </main>
</template>

<style lang="scss">
@use "./styles/general.scss" as *;

.loading-img {
    width: 300px;
    margin: 4rem 0;
    animation: rotating 1s infinite;
}

@keyframes rotating {
    from {
        transform: rotate(0deg);
    }

    to {
        transform: rotate(360deg);
    }
}
</style>
