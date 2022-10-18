<template>
	<view>
		<!-- v-for遍历数组 -->
		<button v-on:click="handleAdd" type="primary" class="margin">
			新增学员
		</button>
		<view v-for="(item,index) in stu" class="box margin">
			序号：{{index}},姓名：{{item.name}},分数：{{item.score}}
		</view>
		<!-- v-for遍历对象 -->
		<view v-for="(value,key) in status" class="box active margin">
			{{key}} 代表 {{value}} 状态
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
				status: {
					'101': '成功',
					'102': '警告',
					'103': '失败'
				}

			}
		},
		methods: {
			handleAdd() {
				this.stu.push({
					name: '灭绝师太',
					score: 70
				})
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
</style>
