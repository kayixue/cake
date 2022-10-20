<template>
	<view>
		<button type="primary" class="margin" @tap="handleAdd">
			新增
		</button>
		<button type="primary" class="margin" @tap="handleEdit">
			编辑
		</button>
		<view class="box margin" v-for="(item,index) in stu">
			姓名:{{item.name}} 分数：{{item.score}}
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				stu: [{
						name: '小宝',
						score: 100
					},
					{
						name: '咪咪',
						score: 80
					},
					{
						name: '肥肥',
						score: 60
					},
				],
			}
		},
		watch:{
			// stu(){//浅监听
			// 	console.log('检测到了stu的变化');
			// 	//实现stu变化所引发的相关逻辑代码
			// 	//例如：将最新的stu数据包存储至本地存储
			// 	uni.setStorage({//数据存储
			// 		key:'stu',
			// 		data:this.stu
			// 	})
			// },
			stu:{//深监听
				handler(){
					console.log('检测到了stu的变化');
					//实现stu变化所引发的相关逻辑代码
					//例如：将最新的stu数据包存储至本地存储
					uni.setStorage({//数据存储
						key:'stu',
						data:this.stu
					})
				},
				deep:true
			}
		},
		methods: {
			handleAdd(){
				this.stu.push({
					name: '猪猪小宝',
					score:70                                                                                                       
				})
			},
			handleEdit(){
				this.stu[1].name="小美女"
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
		text-align: center;
	}
</style>
