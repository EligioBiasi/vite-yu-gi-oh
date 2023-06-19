<template >
    <div class="container">
        <div class="counter-bar">
            <h3>
                found 25 cards
            </h3>
        </div>
        <div class="card-section">
            <SingleCard v-for="card in CardLibrary"
            :monsterName="card.name"
            :monsterType="card.archetype"
            :monsterImage="card.card_images[0].image_url"
            />
        </div>
    </div>
</template>
<script>
import SingleCard from './SingleCard.vue';
import axios from 'axios';

export default {
    name:'CardLibrary',
    data(){
        return {
            CardLibrary:[],
        }
    },
    components:{
        SingleCard,
    },

    created(){
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
  .then( (response) => {
    console.log(response.data.data);
    this.CardLibrary = response.data.data;
  })
  .catch(function (error) {
    console.log(error);
  })
    }

}
</script>
<style lang="scss" scoped>
    div.container{
        width: 1100px;
        margin: 0 auto;
        padding: 1rem;
    }

    div.card-section{
        display: flex;
        flex-wrap: wrap;
        background-color: white;
    }
    div.counter-bar{
        background-color: black;
        h3{
            color: white;
            padding: 1rem;
        }
    }
</style>