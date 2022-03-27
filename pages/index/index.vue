<template>
	<view class="contenting">
		<Search></Search>
		<Preference></Preference>
		<Title></Title>
		<Delicacy></Delicacy>
		<Takeout></Takeout>
	</view>
</template>

<script>
	import Search from './component/search.vue'
	import Preference from './component/preference.vue'
	import Title from './component/title.vue'
	import Delicacy from './component/delicacy.vue'
	import Takeout from './component/takeout.vue'
	export default {
		components: {
			Search,
			Preference,
			Title,
			Delicacy,
			Takeout
		},
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style scoped>
	.contenting {
		margin: 0 15upx;
	}
</style>
