<template >
    <div class="card">
        <img :src="monsterImage" alt="#">

        <h2>
            {{ monsterName }}
        </h2>

        <p>
            {{ monsterType }}
            
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

    props:{
        monsterName: String,
        monsterType: String,
        monsterImage: String,
    }
}
</script>
<style lang="scss" scoped>
    div.card{
        width: calc(100%/5);
        background-color: white;
        padding: 1rem;

        h2{
            color: white;
            text-transform: uppercase;
        }
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