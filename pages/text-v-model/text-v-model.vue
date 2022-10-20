<template>
	<view>
		<view class="">
			{{msg}}
		</view>
		<!-- 单向绑定 -->
		<input type="text" :value="msg" />
		<!-- 双向绑定 -->
		<input type="text" v-model="msg" />
		<!-- 多行文本输入 -->
		<textarea v-model="msg" placeholder=""/>
		<checkbox-group @change="handleChange">
			<checkbox value="lanqiu" >篮球</checkbox>
			<checkbox value="zuqiu" >足球</checkbox>
		</checkbox-group>
		<view v-for="(item,index) in hobby" >
			{{item}}
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				msg:'hello',
				hobby:[]
				
			}
		},
		methods: {
			handleChange(ev){
				console.log(ev)
				console.log(ev.detail.value)
				this.hobby=ev.detail.value
			}
		}
	}
</script>

<style>

</style>
