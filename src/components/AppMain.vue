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
                <h3 class="text-light">Found 62 characters</h3>
            </div>

            <div class="card-section-bottom">
                <div class="container">
                    <div class="row">
                        <div class="col-12">
                            <div class="row row-cols-1 row-cols-md-2 row-cols-lg-5">
                                <div class="col">
                                    <AppCards />
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
    width: 90%;
    margin: 0 auto;
    h3{
        font-size: 1rem;
    }
}

</style>