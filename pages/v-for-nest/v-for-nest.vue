<template>
	<view>
		<view v-for="(item,index) in wulin ">
			<view class="box dark margin" @tap="skillIdx=index">
				门派：{{item.title}} 代表：{{item.represent}}
			</view>
			<view v-if="skillIdx==index">
				<view v-for="(itm,idx) in item.skill" class="box margin margin-left">
					{{itm}}
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				wulin:[
					{
						title:'少林',
						represent:'扫地僧',
						skill:[
							'三十六路拳脚',
							'七十二绝技',
							'易筋经',
							'金钟罩',
							'铁布衫'
						]
					},
					{
						title:'武当',
						represent:'张三丰',
						skill:[
							'梯云纵',
							'太极拳法',
							'纯阳无极功'
						],
						
					}
				],
				skillIdx:-1
			}
		},
		methods: {
			
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
		text-align: center;
	}
</style>
