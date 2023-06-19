<template >
    <div class="container">
        <SingleCard v-for="card in CardLibrary"
        :monsterName="card.name"
        :monsterType="card.archetype"
        :monsterImage="card.card_images[0].image_url"
        />
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
        display: flex;
        flex-wrap: wrap;
    }
</style>