<template>
    <main>
        <CardLibrary />
    </main>
</template>
<script>
import CardLibrary from './CardLibrary.vue'
export default {
    name:'AppMain',
    data(){
        return {

        }
    },
    components:{
        CardLibrary,
    }
    
}
</script>
<style lang="scss" scoped>
    main{
        padding: 2rem 0;
        background-color: #d48f38;
    }
</style>