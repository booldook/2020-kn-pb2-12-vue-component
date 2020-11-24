<template lang='pug'>
	.product-wrapper
		product
</template>

<script>
import Product from './Product.vue';

export default {
	name: 'product-wrapper',
	components: {
		'product': Product,
	}
}
</script>

<style lang='scss' scoped>

</style>