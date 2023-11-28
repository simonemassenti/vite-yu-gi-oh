<script>
import { store } from '../store.js';

export default {
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <select @change="$emit('filter')" v-model="store.selected" name="sel-Archetype"  class="mb-4">
        <option value=""></option>
        <option value="Alien">Alien</option>
        <option value="Ally of Justice">Ally of Justice</option>
        <option value="Ancient Gear">Ancient Gear</option>
    </select>
</template>

<style lang="scss" scoped>
</style>