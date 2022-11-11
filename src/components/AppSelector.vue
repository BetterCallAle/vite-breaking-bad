<script>
import {store} from "../store"

export default {
    name: "AppSelector",
    data(){
        return{
            store
        }
    }
}
</script>

<template>
    <section id="option-selection">
        <div class="container">
            <select name="category" id="select-category" v-model="store.optionValue" @change="$emit('optionChanged')">
                <option value="">Select Category</option>
                <option value="Breaking Bad">Breaking Bad</option>
                <option value="Better Call Saul">Better Call Saul</option>
            </select>
        </div>
    </section>
</template>

<style lang="scss" scoped>

</style>