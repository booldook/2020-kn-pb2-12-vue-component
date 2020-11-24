<template>
	<div class="container">
		<div class="jumbotron">
			<h1>
				{{title}}
				<hr>
				<small class="text-secondary">
					<i class="fa fa-shopping-basket mr-3"></i>
					{{subTitle}}
				</small>
			</h1>
		</div>
		<search-bar v-on:@submit='onSubmit'></search-bar>
	</div>
</template>

<script>
import SearchBar from './components/SearchBar.vue';

export default {
	data() {
		return {
			title: '다팔아 쇼핑몰',
			subTitle: '검색을 통해 상품을 살펴보세요~',
			search: '',
		}
	},
	components: {
		'search-bar': SearchBar
	},
	methods : {
		onSubmit(value) {
			this.search = value;
			alert(this.search);
		}
	}
}
</script>

<style>

</style>