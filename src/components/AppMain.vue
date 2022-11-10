<script>
import {store} from '../store'
import AppCards from './AppCards.vue';

export default {
    name: "AppMain",
    components:{
        AppCards
    },
    data(){
        return{
            store
        }
    }
}
</script>

<template>
    <section id="cards-section">
        <div class="container bg-light py-5">
            <div class="cards-section-top bg-dark p-3 my-4">
                <h3 class="text-light">{{ `Found ${store.characters.length} characters` }}</h3>
            </div>

            <div class="card-section-bottom">
                <div class="container">
                    <div class="row">
                        <div class="col-12">
                            <div class="row g-4 row-cols-1 row-cols-md-2 row-cols-lg-5">
                                <div class="col" v-for="character in store.characters" :key="store.characters.char_id">
                                    <AppCards :character="character"/>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
.cards-section-top{
    h3{
        font-size: 1rem;
    }
}

</style>