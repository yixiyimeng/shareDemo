<template>
	<view>
		<view>
			<view>text 生成的文本内容</view>
			<view>foregroundColor 二维码颜色</view>
			<view>backgroundColor 背景颜色</view>
			<view>makeOnLoad 是否自动生成</view>
			<view>makeComplete 生成回调</view>
			<view>logo 中间的小logo</view>
		</view>
		<view class="block">

			<view class="component">
				<uni-qrcode cid="qrcode1446" text="uQRCode" foregroundColor="#2b9939" logo="https://img-cdn-qiniu.dcloud.net.cn/uploads/avatar/000/72/20/93_avatar_max.jpg"
				 makeOnLoad @makeComplete="qrcode1446Complete" />
			</view>
		</view>

		<view class="block">
			<view class="component" style="background-color: #f0f0f0;">
				<uni-qrcode cid="qrcode2233" ref="qrcode2233" text="uQRCode" />
			</view>
			<view class="operate">
				<button type="primary" size="mini" @click="qrcodeClick()">点击生成</button>
			</view>
		</view>


	</view>
</template>

<script>
	import uniQrcode from '@/components/uni-qrcode/uni-qrcode'

	export default {
		components: {
			uniQrcode
		},
		data() {
			return {

			}
		},
		methods: {
			qrcodeClick() {
				this.$refs.qrcode2233.make()
			},
			qrcode1446Complete(e) {
				console.log(e)
			}
		}
	}
</script>

<style>
	page {
		background-color: #f0f0f0;
	}

	.block {
		margin-top: 20rpx;
		padding: 20rpx;
		background-color: #ffffff;
	}

	.title {
		font-size: 30rpx;
		font-weight: 500;
		padding-bottom: 20rpx;
		line-height: 1.5;
	}

	.tips {
		font-size: 24rpx;
		color: #888888;
	}

	.component {
		display: flex;
		justify-content: center;
		padding: 20rpx 0;
	}

	.operate {
		display: flex;
		justify-content: center;
		padding: 20rpx 0;
	}
</style>
