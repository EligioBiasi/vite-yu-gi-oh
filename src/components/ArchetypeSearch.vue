<template>
    <select name="" id="" v-model="store.ArchetypeName" @change="emitSearch">
        <option>
            select archetype
        </option>

        <option :value="archetype.archetype_name" v-for="archetype in store.ArchetypeLibrary ">
            {{ archetype.archetype_name }}
        </option>
        
    </select>
</template>

<script>
import { store } from "../store.js";

export default {
    data(){
        return {
            store,
        }
    },

    methods: {
    emitSearch() {
      this.$emit("Search");
    },
  },
}
</script>

<style lang="scss" scoped>
    select{
        margin-bottom: 1rem;
        width: 150px;
        height: 20px;
    }
</style>