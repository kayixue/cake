<template>
	<view>
		<view class="flex margin">
			<input type="text" value="">
			<button type="primary">发送</button>
		</view>
		<!-- <view class="box"></view> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
input{
	height: 100upx;
	border: 1upx solid #9BA7Bf;
	flex: 1;
}
.flex{
	display: flex;
	justify-content: center;
}
.margin{
	margin: 10upx;
}
.box{
	background-color: #9BA7Bf;
	text-align: center;
	padding:0 30upx
}
</style>
