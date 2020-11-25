<template lang='pug'>
	.product-wrapper
		product(v-for='v in products' v-bind:key='v.id' v-bind:product='v')
</template>

<script>
import Product from './Product.vue';
import axios from 'axios';

export default {
	name: 'product-wrapper',
	props: ['search'],
	data() {
		return {
			products: [],
		}
	},
	components: {
		'product': Product,
	},
	watch: {
		search: async function(newValue, oldValue) {
			try {
				let r = await axios.get('/json/products.json');
				this.products = r.data.products;
			}
			catch(e) {
				console.log(e);
			}
		}
	}
}
</script>

<style lang='scss' scoped>
	.product-wrapper {display: flex; flex-wrap: wrap; align-items: flex-start;}
</style>