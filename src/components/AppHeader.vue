<template>
    <header>
        <img src="https://vignette1.wikia.nocookie.net/yugiohenespanol/images/a/aa/Yugioh_anime_logo.jpg/revision/latest?cb=20130310042737&path-prefix=es" alt="">
        <h1>
            Yu-Gi-Oh Api
        </h1>
    </header>
</template>
<script>
export default {
    name:'AppHeader',
    data(){
        return {

        }
    },
}
</script>
<style lang="scss" scoped>
    header{
        padding: 1rem;
        display: flex;
        align-items: center;

        img{
            width: 75px;
            margin-right: .7rem;
        }
    }
</style>