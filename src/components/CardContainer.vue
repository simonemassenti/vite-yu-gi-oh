<script>
import Card from './Card.vue';
import { store } from '../store.js';
export default {
    components: {
    Card
},
data() {
    return {
        store
    }
}
}
</script>

<template>
    <div class="container-fluid p-4">
        <div class="container" >
            <div class="row">
                <div class="col" v-for="card in store.cards">
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