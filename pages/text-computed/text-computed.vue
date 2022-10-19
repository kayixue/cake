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
				status:2 //0全部 1及格 2不及格
			}
		},
		computed:{
			reMsg(){
				return this.msg.split('').reverse().join('')
			},
			filterStu(){
				let {status,stu} = this
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
