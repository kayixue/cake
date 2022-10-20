<template>
	<view>
		<!-- <view class="">
			{{msg}}
		</view> -->
		<!-- 不使用computed -->
		<!-- <view class="">
			{{msg.split('').reverse().join('')}}
		</view> -->
		<!-- 使用computed -->
		<!-- <view class="">
			{{reMsg}}
		</view> -->
		<view class="flex">
			<view class="box dark" @tap="status=0">
				全部
			</view>
			<view class="box"@tap="status=1">
				及格
			</view>
			<view class="box"@tap="status=2">
				不及格
			</view>
		</view>
		<view class="box margin" v-for="(item,index) in filterStu">
			姓名：{{item.name}} 分数：{{item.score}}
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				msg:"hello hello",
				stu:[
					{name:'张',score:100},
					{name:'李',score:70},
					{name:'肥肥',score:50}
				],
				status:9 //0全部 1及格 2不及格
			}
		},
		computed:{
			reMsg(){
				return this.msg.split('').reverse().join('')
			},
			filterStu(){
				// var {status,stu} = this  解包
				var status = this.status
				let stu = this.stu
				switch (status){
					case 1:
						let arr = stu.filter((item)=>{
							return item.score >=60
						})
						return arr
					case 2:
						return stu.filter((item)=>{
							return item.score <60
						})
					default:
						return stu
				}
			}
		},
		methods: {
			
		}
	}
</script>

<style>
.margin {
		margin: 20upx;
	}

	.box {
		height: 100upx;
		background-color: #65728c;
		text-align: center;
		color: #f1bcae;
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
	.dark {
		background-color: #4f37f4;
	}
</style>
