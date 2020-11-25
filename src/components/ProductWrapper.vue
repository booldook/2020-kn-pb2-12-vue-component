<template lang='pug'>
	.product-wrapper
		product
</template>

<script>
import Product from './Product.vue';

export default {
	name: 'product-wrapper',
	props: ['search'],
	components: {
		'product': Product,
	}
}
</script>

<style lang='scss' scoped>
	.product-wrapper {display: flex; flex-wrap: wrap; align-items: flex-start;}
</style>