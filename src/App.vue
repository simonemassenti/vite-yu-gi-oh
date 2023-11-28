<script>
import AppHeader from './components/AppHeader.vue';
import CardContainer from './components/CardContainer.vue';
import axios from "axios";
import { store } from "./store.js";
export default {
    components: {
        AppHeader,
        CardContainer
    },
    data() {
        return{
            store
        }
    },
    created() {
        axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
        .then((resp) => {
            this.store.cards = resp.data.data;
        });
    }
}

</script>

<template>
    <AppHeader />
    <CardContainer />


</template>

<style lang="scss">
@use "./style/general.scss"
</style>
