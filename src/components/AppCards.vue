<script>
export default {
    props: {
        character: Object
    }
}
</script>

<template>
    <div class="ms_card text-center">
        <div class="ms_card-top">
            <img :src="character.img"
                :alt="`Foto di ${character.name}`" class="w-100">
        </div>

        <div class="ms_card-bottom">
            <h3 class="ms_card-title text-light">{{ character.name }}</h3>

            <h4 class="ms_card-subtitle ">{{ character.category }}</h4>
            <p class="ms_card-subtitle">{{ character.status }}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

.ms_card {
    height: 100%;
        background-color: $main-bg;
        padding: 1rem .8rem;
    
        .ms_card-bottom {
            .ms_card-title {
                font-size: 1rem;
                text-transform: uppercase;
                margin-top: 1rem
            }
    
            h4 {
                font-size: .7rem;
            }
    
            p {
                font-size: .6rem;
        }

        .ms_card-subtitle {
            color: $font-gray-color;
        }
    }
}
</style>