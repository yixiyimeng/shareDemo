<template>
	<view class="container">
		<view>
			<view>serverUrl：图片上传地址</view>
			<view>limit 图片上传数量限制 默认9</view>
			<view>value 默认回填图片列表</view>
			<view>complete 图片上传完成后的回调，返回图片列表</view>
			<view>remove 图片删除后的回调</view>
		</view>
		<upload :serverUrl="serverUrl"  @complete="result" @remove="remove"></upload>
	</view>
</template>

<script>
	//实际使用需要传入上传地址，以及上传接口返回数据进行调整组件
	import upload from '@/components/upload/upload'
	export default {
		components: {
			upload
		},
		data() {
			return {
				imageData: [],
				//上传地址
				serverUrl:"http://upload.cn"
			}
		},
		methods: {
			result: function(e) {
				console.log(e)
				this.imageData = e.imgArr;
			},
			remove: function(e) {
				//移除图片
				console.log(e)
				let index = e.index
			}
		}
	}
</script>

<style>
	page{
		background: #fff;
	}
	.container {
		padding: 20rpx 0 120rpx 0;
		box-sizing: border-box;
	}

	.header {
		padding: 80rpx 90rpx 60rpx 90rpx;
		box-sizing: border-box;
	}

	.title {
		font-size: 34rpx;
		color: #333;
		font-weight: 500;
	}

	.sub-title {
		font-size: 24rpx;
		color: #7a7a7a;
		padding-top: 18rpx;
	}
	.tui-box-upload{
		padding-left: 25rpx;
		box-sizing: border-box;
	}
</style>
