<template lang='pug'>
	.container
		.jumbotron
			h1 {{title}}
				hr
				small.text-secondary
					i.fa.fa-shopping-basket.mr-3
					span {{subTitle}}
		search-bar(v-on:@submit="onSubmit")
		transition(name='fade' mode='out-in' appear)
			product-wrapper(v-bind:search='search' v-show='search.length')
</template>

<script>
// 자식이 부모에게 데이터를 보낼때는 이벤트($emit)로 보낸다.
// 부모로부터 데이터를 받을때는 변수(props)로 받는다.
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