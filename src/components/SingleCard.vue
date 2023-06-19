<template >
    <div class="card">
        <img src="https://www.calabriamagnifica.it/wp-content/uploads/2023/03/imagine-john-lennon.jpg" alt="">
        <h2>
            prova
        </h2>
        <p>
            altra prova
        </p>
    </div>
</template>
<script>
export default {
    name:'SingleCard',
    data(){
        return {

        }
    },
}
</script>
<style lang="scss" scoped>
    div.card{
        width: calc(100%/5);
        background-color: white;
        padding: 1rem;
        

        h2,p{
            background-color: #d48f38;
            padding: 1rem 0;
            text-align: center;
        }
        img{
            width: 100%;
            display: block;
        }
    }
</style>