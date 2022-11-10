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
            <img src="https://images.amcnetworks.com/amc.com/wp-content/uploads/2015/04/cast_bb_700x1000_walter-white-lg.jpg"
                alt="">
        </div>

        <div class="ms_card-bottom text-center">
            <h3 class="ms_card-title text-light">Nome</h3>

            <h4 class="ms_card-subtitle ">Serie</h4>
            <p class="ms_card-subtitle">Morto</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../styles/partials/variables" as *;

.ms_card {
    background-color: $main-bg;
    padding: 1rem .8rem;

    .ms_card-bottom {
        .ms_card-title {
            font-size: 1.3rem;
            margin-top: 1rem
        }

        h4 {
            font-size: 1.1rem;
        }

        .ms_card-subtitle {
            color: $font-gray-color;
        }
    }
}
</style>