<script>
import Card from './Card.vue';
import { store } from '../store.js';
import AppSelect from './AppSelect.vue';
import axios from 'axios';
export default {
    components: {
    Card,
    AppSelect
},
data() {
    return {
        store,
        num: 20,
        offset: 0
    }
},
methods: {
    filter() {
        axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php", {
            params: {
                num: this.num,
                offset: this.offset,
                archetype: this.store.selected
            }
        })
        .then((resp) => {
            this.store.cards = resp.data.data;
        })
    }
}
}
</script>

<template>
    <div class="container-fluid p-4">
        <AppSelect @filter="filter"/>

        <div class="container" >
            <div class="row row-cols-5">
                <div class="col mb-2 p-2" v-for="card in store.cards">
                    <Card :image="card.card_images[0].image_url" :name="card.name" :archetype="card.archetype"/>
                </div>
                
            </div>
            
        </div>
    </div>

</template>

<style lang="scss" scoped>
.container-fluid {
    background-color: orange;
}

.container {
    background-color: white;
}
</style>