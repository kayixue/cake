<template>
	<view>
		<!-- 基本菜单切换 -->
		<view class="flex">
			<view :class="['box',{'dark':isActive}]" @tap="handleTap(true)">
				菜单一
			</view>
			<view :class="['box',{'dark':!isActive}]" @tap="handleTap(false)">
				菜单二
			</view>
		</view>
		<view class="box cont margin" v-if="isActive">
			内容一
		</view>
		<view class="box cont margin" v-else="!isActive">
			内容二
		</view>
		<!-- 拓展菜单切换 -->
		<view class="flex">
			<view v-for="(item,index) in tabsArr" 
			:class="['box',{'dark':index==tabIdx}]"
			@tap="tabIdx=index">
				{{item}}
			</view>
		</view>
		<view v-for="(item,index) in tabsArr" class="box cont margin" v-if="index==tabIdx">
			这是{{item}}的内容
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isActive:false,
				tabsArr:[
					'首页','新闻','产品','联系我们','招聘'
				],
				tabIdx:0
			}
		},
		methods: {
			handleTap(bool){
				this.isActive=bool
				
			}
		}
	}
</script>

<style>
.flex{
	display: flex;
	justify-content: center;
}
.margin {
		margin: 10upx;
	}

	.box {
		height: 100upx;
		background-color: #65728c;
		text-align: center;
		color: #1a0032;
		font-size: 30upx;
		line-height: 100upx;
		padding: 0 30upx;
	}

	.box.active {
		background-color: #1900f5;
	}

	.box1 {
		height: 200upx;
		background-color: #708e00;
	}
	.dark
	{
		color: #e9eadb;
		text-align: center;
		background-color: #0f0118;
	}
	.box.dark{
		height: 100upx;
		line-height: 100upx;
	}
	.margin-left{
		color: #e9e9e9;
		text-align: center;
	}
	.cont{
		color: #344209;
		height: 200upx;
		font-weight: 200upx;
		line-height: 200upx;
		background-color: #d6c4ed;
		font-size: 30upx;
		display: flex;
	}
</style>
