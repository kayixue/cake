<template>
	<view>
		<button v-on:tap="handleShow "type="primary" class="margin">
			控制元素显示
		</button>
		<view v-if="isShow" class="box margin">
			演示v-if
		</view>
		<view v-else-if="isShow2" class="box margin">
			演示v-elif
		</view>
		<view v-else class="box margin">
			v-else
		</view>
		<view v-show="isShow" class="box box1 margin">
			演示v-show
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isShow:false,
				isShow2: false
			}
		},
		methods: {
			handleShow(){
				this.isShow= !this.isShow
			}
		}
	}
</script>

<style>
.margin {
		margin: 10upx;
	}

	.box {
		height: 200upx;
		background-color: #65728c;
		text-align: center;
		color: #4f37f4;
		font-size: 50upx;
		line-height: 200upx;
	}

	.box.active {
		background-color: #1900f5;
	}

	.box1 {
		height: 200upx;
		background-color: #708e00;
		}
</style>
