<template lang='pug'>
	.container
		.jumbotron
			h1 {{title}}
				hr
				small.text-secondary
					i.fa.fa-shopping-basket.mr-3
					span {{subTitle}}
		search-bar(v-on:@submit="onSubmit")
		product-wrapper
</template>

<script>
import SearchBar from './components/SearchBar.vue';
import ProductWrapper from './components/ProductWrapper.vue';

export default {
	data() {
		return {
			title: '다팔아 쇼핑몰',
			subTitle: '검색을 통해 상품을 살펴보세요~',
			search: '',
		}
	},
	components: {
		'search-bar': SearchBar,
		'product-wrapper': ProductWrapper,
	},
	methods : {
		onSubmit(value) {
			this.search = value;
		}
	}
}
</script>

<style lang='scss'>

</style>