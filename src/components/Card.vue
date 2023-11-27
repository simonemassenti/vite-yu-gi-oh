<script>
export default {
    props: {
        image: String,
        name: String,
        archetype: String
    }
}
</script>

<template>
    <div class="text-center p-1 my-4">
        <img :src="image" :alt="name">
        <p>{{ name }}</p>
        <h6>{{ archetype }}</h6>
    </div>
</template>

<style lang="scss" scoped>
    div{
        width: 200px;
        background-color: orange;
        padding-bottom: 2rem;

        img {
            width: 100%;
        }

        p{
            text-transform: uppercase;
            font-weight: bold;
            color: white;
            margin-top: 5px
        }

    }


</style>