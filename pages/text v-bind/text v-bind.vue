<template>
	<view>
		<!-- 属性：class value style -->
		<view class="box" v-bind:class="isAcitve?'active':''">

		</view>
		<view v-bind:class="['box',isAcitve?'active':'']">

		</view>
		<view v-bind:class="['box',{'active':isActive}]">

		</view>
		<!-- <image src="../../static/logo.png" mode=""></image>
		<image src="../../static/img/recommend2.jpg" mode=""></image> -->
		<!-- <image v-bind:src="isLogoin?'../../static/img/recommend2.jpg':'../../static/logo.png'" mode=""></image> -->
		<image v-bind:src="imgs[loginState]" mode=""></image>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isAcitve: true,
				isLogoin: true,
				imgs:[
					'../../static/logo.png',
					'../../static/img/recommend2.jpg'
				],
				loginState:0,
				
			}
		},
		methods: {

		}
	}
</script>

<style>
	.box {
		height: 100px;
		width: 100px;
		border: 1px solid red;
	}

	.box.active {
		background-color: aqua;
	}

	image {
		width: 100px;
		height: 100px;
	}
</style>
