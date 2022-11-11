<script>
import {store} from "../store"
export default{
    name: "AppCounter",
    data(){
        return{
            store
        }
    },
    computed:{
        counterPhrases(){
            if(!this.store.characters.length){
                return 'No characters found'
            } else{
                return `Found ${this.store.characters.length} characters`
            }
        }
    }
}
</script>

<template>
    <div class="counter bg-dark p-3 my-2">
        <h3 class="text-light">Found {{store.characters.length}} characters</h3>
    </div>
</template>