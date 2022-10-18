<template>
	<view>
		<view v-for="(item,index) in list" v-bind:key="item" class="box dark margin">
			<checkbox />
			
			[{{item}}]
			<text @tap="handleDelate(index)" class="margin-left">删除</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list:[
					'青海长云暗雪山',
					'孤城遥望玉门关',
					'黄沙百战穿金甲',
					'不破楼兰终不还'
				]
			}
		},
		methods: {
			handleDelate(idx){
				this.list.splice(idx,1)
			}
			
		}
	}
</script>

<style>
.margin {
		margin: 10upx;
	}

	.box {
		height: 100upx;
		background-color: #65728c;
		text-align: center;
		color: #4f37f4;
		font-size: 30upx;
		line-height: 100upx;
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
	}
	.margin-left{
		color: #e9e9e9;
		text-align: right;
	}
</style>
