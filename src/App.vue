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
        axios.get("https://www.breakingbadapi.com/api/characters").then((resp) => {
            this.store.characters = resp.data;
            console.log(this.store);
        })
    }
  
}

</script>

<template>
    <AppHeader />

    <main>
        <AppSelector />
        <AppMain />
    </main>
</template>

<style lang="scss">
@use "./styles/general.scss" as *;

</style>
