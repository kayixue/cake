<template>
	<view>
		<button v-on:tap="handleBg" type="primary" class="margin">
			控制激活
		</button>
		<button @tap="handleBg" type="primary" class="margin">
			@控制激活
		</button>
		<view class="box margin" v-bind:class="{active:isActive}">
		</view>
		<button v-on:click="handleBg" type="primary" class="margin">
			控制激活2
		</button>
		<button @click="handleBg" type="primary" class="margin">
			@控制激活2
		</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isActive: false,

			}
		},
		methods: {
			handleBg() {
				console.log(123)
				this.isActive = !this.isActive
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
		color: #ff0027;
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
