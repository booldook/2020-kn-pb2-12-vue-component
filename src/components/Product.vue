<template lang='pug'>
	.product
		img.img.w-100(v-bind:src="require(`../assets/products/${product.src}`)")
		.title {{product.name}}
		.price {{product.price}}
</template>

<script>
export default {
	name: 'product',
	props: ['product']
}
</script>

<style lang='scss' scoped>
	.product {
		flex: 33.3333% 0 0;
		padding: 1%;
		img.img {}
		.title {background-color: #222; color: #fff; padding: 1em; font-size: 1.25em;}
		.price {background-color: #222; color: #ccc; padding: 0 1em 1em 1.25em;}
	}
</style>