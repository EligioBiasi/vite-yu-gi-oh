<template >
    <div class="container">
        <div>

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
  .then(function (response) {
    console.log(response);
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
    }
</style>