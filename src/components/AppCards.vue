<script>
export default {
    props: {
        character: Object
    }
}
</script>

<template>
    <div class="ms_card">
        <div class="ms_card-top">
            <img :src="character.img"
                :alt="`Foto di ${character.name}`">
        </div>

        <div class="ms_card-bottom text-center">
            <h3 class="ms_card-title text-light">{{ character.name }}</h3>

            <h4 class="ms_card-subtitle ">{{ character.category }}</h4>
            <p class="ms_card-subtitle">{{ character.status }}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

.ms_card {
    background-color: $main-bg;
    padding: 1rem .8rem;
    min-height: 380px;
    .ms_card-bottom {
            .ms_card-title {
                font-size: 1rem;
                    text-transform: uppercase;
                    margin-top: 1rem
                }
                
                h4 {
                    font-size: .9rem;
                }
                
                p {
                    font-size: .8rem;
        }

        .ms_card-subtitle {
            color: $font-gray-color;
        }
    }
}
</style>