<template>
	<view>
		<!-- //试图区 -->
		<view class="">
			使用数据驱动视图
		</view>
		<view class="">{{msg}}</view>
		<input type="text" v-model="msg"/>
	</view>
</template>

<script>
	export default {
		data() { //Modle数据层
			return {
				msg:'Hello Uniapp'
			}
		},
		methods: {
			
		}
	}
</script>

<style>

</style>
