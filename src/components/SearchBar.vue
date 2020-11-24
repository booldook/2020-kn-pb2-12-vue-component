<template lang="pug">
	form(id='search-form' name='search-form' v-on:submit.prevent='onSubmit')
		input.form-control.search-input(v-model='search' type='text' placeholder='검색할 상품을 입력하세요.' autofocus)
		i.fa.fa-times-circle.bt-reset(v-show='search.length' v-on:click='onReset')
</template>

<script>
export default {
	name: 'search-bar',
	data() {
		return {
			search: ''
		}
	},
	methods: {
		// 부모에게 데이터를 보낼때는 이벤트로 보낸다.
		// 부모로부터 데이터를 받을때는 변수로 받는다.
		
		onSubmit(e) {
			// $emit == dispatchEvent
			this.$emit('@submit', this.search);
		},
		
		onReset(e) {
			this.search = '';
		}
	}
}
</script>

<style lang="scss" scoped>
	form {
		margin: 2em 0;
		border-top: 1px solid #ccc;
		border-bottom: 1px solid #ccc;
		padding: 1em;
		position: relative;
		input.search-input {
			&:focus {
				outline: none;
				box-shadow: none;
			}
		}
		.bt-reset {
			position: absolute;
			top: 50%; right: 24px;
			transform: translateY(-50%);
			cursor: pointer;
		}
	}
</style>