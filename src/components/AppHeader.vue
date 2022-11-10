<script>
export default{
    name: "AppHeader"
}
</script>

<template>
    <header>
        <img src="../assets/img/logo.png" alt="Logo di Breaking Bad">
        <h1>Breaking Bad API</h1>
    </header>
</template>

<style lang="scss" scoped>
    header{
        color: white;
        padding: 1rem;
        
        img{
            width: 50px;
        }

        h1{
            display: inline-block;
            margin-left: .7rem;
            vertical-align: middle;
        }
    }

</style>