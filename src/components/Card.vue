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
	<div class="text-center p-1 h-100 mt-2 border d-flex flex-column justify-content-between rounded-3">
		<img class="rounded-3" :src="image" :alt="name">
		<p>{{ name }}</p>
		<h6>{{ archetype }}</h6>
	</div>
</template>

<style lang="scss" scoped>
	div{

		background-color: orange;
		img {
			width: 100%;
		}

		p{
			text-transform: uppercase;
			font-weight: bold;
			color: white;
		}

	}


</style>