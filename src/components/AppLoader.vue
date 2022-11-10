<script>
export default {
    name: "AppLoader"
}
</script>

<template>
    <div class="loading text-center">
        <img src="../../src/assets/img/loading.png" alt="Walter White Loading Meme" class="loading-img">
        <span class="loading-txt text-light d-block">Loading...</span>
    </div>
</template>

<style lang="scss" scoped>
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