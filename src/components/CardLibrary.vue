<template >
    <div class="container">
        <div>
            <ArchetypeSearch @Search="requestDataFromApi"/>
        </div>
        <div class="counter-bar">
            <h3>
                Found {{CardLibrary.length}} cards
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
import ArchetypeSearch from './ArchetypeSearch.vue';
import axios from 'axios';
import { store } from "../store.js";

export default {
    name:'CardLibrary',
    data(){
        return {
            CardLibrary:[],
            store,
        }
    },
    components:{
        SingleCard,
        ArchetypeSearch,
    },

    created(){
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
        .then( (response) => {
            this.CardLibrary = response.data.data;
        });

        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then( (response) => {
            this.store.ArchetypeLibrary = response.data ;
            console.log(response.data);
        });
    },

    methods: {
    requestDataFromApi() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php", {
          params: {
            num: 20,
            offset: 0,
            archetype: this.store.ArchetypeName,
          },
        })
        .then((response) => (this.CardLibrary = response.data.data));
    },
  },

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