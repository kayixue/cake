<template>
	<!-- //事件修饰符基本使用 -->
	<view>
		<!-- <view class="box" @click="handleAlter">
			<view class="box" @click="handleAlter">
				<view class="box" @click.stop="handleAlter">
					
				</view>
			</view>
		</view> -->
		<!-- 应用场景：遮罩弹窗 -->
		<view class="" @click="isShow=true">
			显示
		</view>
		<view class="cover" v-if="isShow" @click="isShow=false">
			<view class="pop" @click.stop>
				<input type="text" value="">
				<button type="default" @click="isShow=false">关闭</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isShow:false
			}
		},
		methods: {
			handleAlter(){
				alert(123)
			}
		}
	}
</script>

<style>
.box{
	padding: 50upx;
	border: 1upx solid #333;
}
.cover{
	height: 100%;
	width: 100%;
	position: fixed;
	top: 0;
	left: 0;
	background-color: #858386;
}
.pop{
	margin: 100upx 30upx;
	background-color: #dcd9de;
	height: 200upx;
}
</style>
